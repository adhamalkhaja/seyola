---
name: seyola-upgrade
description: |
  Check for and install Seyola Skills updates. Run when user says
  "upgrade seyola", "update skills", "seyola update", or when the
  preamble detects UPGRADE_AVAILABLE.
---

# Seyola Upgrade

Check for updates and upgrade Seyola Skills to the latest version.

---

## Step 0: Check for Updates

```bash
_UPD=$(~/.claude/skills/seyola/bin/seyola-update-check 2>/dev/null || true)
echo "${_UPD:-UP_TO_DATE}"
```

**If output is empty or `UP_TO_DATE`:** Tell the user "Seyola Skills is up to date." and stop.

**If `JUST_UPGRADED <old> <new>`:** Tell the user "Running Seyola Skills v{new} (just updated!)" Then read CHANGELOG.md, summarize what's new between the old and new versions in 3-5 bullets. Stop.

**If `UPGRADE_AVAILABLE <old> <new>`:** Proceed to Step 1.

---

## Step 1: Ask the User

Via AskUserQuestion:

> Seyola Skills **v{new}** is available (you have v{old}). What would you like to do?
>
> - **A) Upgrade now** (recommended)
> - **B) Not now** (ask again later)
> - **C) Always upgrade automatically** (never ask again)

**If A:** Proceed to Step 2.

**If B:** Write snooze marker and stop:
```bash
SEYOLA_HOME="$HOME/.seyola"
SNOOZE_FILE="$SEYOLA_HOME/update-snoozed"
# Read current snooze level (escalates: 1→2→3)
CURRENT_LEVEL=0
if [ -f "$SNOOZE_FILE" ]; then
  CURRENT_LEVEL=$(cat "$SNOOZE_FILE" | cut -d' ' -f2)
fi
NEW_LEVEL=$((CURRENT_LEVEL + 1))
[ "$NEW_LEVEL" -gt 3 ] && NEW_LEVEL=3
echo "{new} $NEW_LEVEL $(date +%s)" > "$SNOOZE_FILE"
```
Tell the user: "Got it. I'll ask again in [24h/48h/7d based on level]."

**If C:** Save auto-upgrade preference and proceed to Step 2:
```bash
~/.claude/skills/seyola/bin/seyola-config set auto_upgrade true
```

---

## Step 2: Detect Install Type

```bash
SEYOLA_HOME="$HOME/.seyola"
INSTALL_PATH=$(cat "$SEYOLA_HOME/install-path" 2>/dev/null || echo "")
echo "INSTALL_PATH: $INSTALL_PATH"

# Check if git repo
if [ -n "$INSTALL_PATH" ] && [ -d "$INSTALL_PATH/.git" ]; then
  echo "TYPE: git"
else
  echo "TYPE: vendored"
fi
```

---

## Step 3: Perform Upgrade

**Save old version first:**
```bash
SEYOLA_HOME="$HOME/.seyola"
INSTALL_PATH=$(cat "$SEYOLA_HOME/install-path" 2>/dev/null || echo "$HOME/.claude/skills/seyola")
OLD_VERSION=$(cat "$INSTALL_PATH/VERSION" 2>/dev/null || echo "unknown")
echo "$OLD_VERSION" > "$SEYOLA_HOME/just-upgraded-from"
```

**If git install:**
```bash
cd "$INSTALL_PATH"
git fetch origin
git reset --hard origin/main
./setup
```

**If vendored (no .git):**
Tell the user: "Your install isn't a git clone. To upgrade, run:"
```
cd ~/.claude/skills/seyola && git pull && ./setup
```
Or: "Re-clone from the repo and run ./setup again."

---

## Step 4: Clear Snooze + Show What's New

```bash
rm -f "$HOME/.seyola/update-snoozed"
rm -f "$HOME/.seyola/last-update-check"
```

Read `CHANGELOG.md` from the upgraded install. Summarize what's new between the old version and the new version.

Present as 3-5 bullets grouped by theme. Keep it user-facing... what they can now DO, not implementation details.

---

## Step 5: Return

Tell the user the upgrade is complete and they can continue working. If this was triggered from another skill's preamble, return control to that skill.

---

## Inline Upgrade Flow (called from preamble)

When another skill's preamble runs `seyola-update-check` and gets `UPGRADE_AVAILABLE`:

1. Check if `auto_upgrade` is `true` in config → if yes, run Step 2-4 silently
2. Otherwise, run Step 1 (ask the user)
3. After upgrade (or snooze), return to the original skill
