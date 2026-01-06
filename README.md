# Table of Contents

- [Adventure Map Spells Overview](#adventure-map-spells-overview)
- [Known Issues](#known-issues)
- [For Modders](#for-modders)
- [TODOs](#todos)
- [Changelog](#changelog)

---

# Adventure Map Spells Overview

![Spells](https://raw.githubusercontent.com/vcmi-mods/adventure-spells-pack/refs/heads/vcmi-1.7/screenshots/screen05.png)

## Elemental Abilities

### **Air**
- **Accuracy**
- **Clarity**
- **Darkness**
- **Divine Spirit**
- **Fleet Foot**
- **Power of Haste**

### **Earth**
- **Dead Luck**
- **Death Call**
- **Dwarven Luck**
- **Herald of Death**
- **Hold Ground**
- **Power of Stone**

### **Fire**
- **Demonic Power**
- **Rise Demons**
- **Shattering Strike**

### **Water**
- **Benediction**
- **Channel Power**
- **Seafaring**
- **Whirlpool Protection**

### Global Abilities

- **Arcane Protection**
- **Empathy**
- **Griffin Eye**
- **Magic Cushion**
- **Negotiations**

---

# Known Issues

> ![Warning] 
> Currently no sounds in the mod; 
> Lacks indication that spells are in use the unit window.
> Casts per day bug: [#6659](https://github.com/vcmi/vcmi/issues/6659).

---

# For Modders

## Pitfalls
1. Mod is standarized for **camelCase naming convention** also to files and folders, to avoid future typos and make easier to edit and generate (e.g. shell scripts). While working on the project, I noticed that naming files like `spellIcon.png` instead of `spellIconBenediction.png` could create more recognizable patterns.


2. **Icons** will replace each other if won't be in its folder, for example: 
- accuracy/content/sprites/**accuracy**/*.png 
- clarity/content/sprites/**clarity**/*.png

Correct paths expample:

```
// herealdOfDeath.json example
...
"graphics": {
      "iconBook": "heraldOfDeath/spellBook",
    	"iconScroll": "heraldOfDeath/spellScroll",
    	"iconScenarioBonus": "heraldOfDeath/spellBonus",
    	"iconEffect": "heraldOfDeath/spellEffect"
    },
...
```
---

## Data sets

Were helpful for AI prompts and documentation.

### Spells added
```
json_data='{
    "air": ["accuracy", "clarity", "darkness", "divineSpirit", "fleetFoot", "powerOfHaste"],
    "earth": ["deadLuck", "deathCall", "dwarvenLuck", "heraldOfDeath", "holdGround", "powerOfStone"],
    "fire": ["demonicPower", "raiseDemons", "shatteringStrike"],
    "water": ["benediction", "channelPower", "seafaring", "whirlpoolProtection"],
    "global": ["arcaneProtection", "empathy", "griffinEye", "magicCushion", "negotiations"]
}'
```


### Submods filesystem pattern

```
/{$element} 
/{$element}/mod.json 
/{$element}/mods
/{$element}/mods/{$spell}
/{$element}/mods/{$spell}/mod.json
/{$element}/mods/{$spell}/content/sprites/*.png
/{$element}/mods/{$spell}/content/sounds/*.ogg
/{$element}/mods/{$spell}/content/config/spells/{$spell}.json
```
---

## TODOs

1. Create an optionable submod:

- [ ] spells duration for 7 days
- [ ] spells negates each other to avoid it's cumulation
- [ ] spells costs knowledge or lowers maximum mana
- [ ] create cancelation spell
- [ ] readjust spells cost

2. Sounds:

- [ ] add sounds

3. Bug Fixes

- [ ] `WARN [initialize] mod - Spell: target type empty - assumed NO_TARGET.`
- [ ] `ERROR [initialize] mod - Spell: no positiveness specified, assumed NEUTRAL.`
- [ ] redundancy in target types (see client log)

# Changelog

## Version 1.5

### Modularization

- [x] Spells are now fully "pickable" in the Launcher. The main change of the update.


### Naming Conventions

- [x] Standardized all file and directory names to begin with lowercase letters. Names with multiple words are now using camelCase for improved clarity.

### Path Fixes

- [x] **Spell Paths:** Resolved incorrect spell paths. (work in progress)
- [x] **Icon Paths:** Corrected various icon paths. (work in progress)
- [x] **Translation Paths:** Fixed issues with translation paths. (work in progress)


### Documentation

- [x] Added a **README.md** to the GitHub repository.
- [x] Included documentation for the mod in the VCMI Launcher (in English).

### Other

- [x] Created folders for sound assets.

---
