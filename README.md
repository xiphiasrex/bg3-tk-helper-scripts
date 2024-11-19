# bg3-tk-helper-scripts
 Helper scripts for testing in BG3 modding toolkit

## Contents
- [Setup Options](#setup-options)
- [Usage](#usage)
    - [Checks and Saving Throws](#checks-and-saving-throws)
    - [Spawning Treasure](#spawning-treasure)
    - [Spawning Creatures (WIP)](#spawning-creatures)
- [Other Info](#other-info)


## Setup Options

1. Copy any script file(s) you want to use to \Data\Mods\MODNAME_UUID\Story\RawFiles\Goals
2. Copy the script contents into an existing osiris script for your mod
3. ~~Set the Util as a dependency from Project Settings. Either:~~
    - ~~Install from the in-game mod manager~~
    - ~~Download pak file from mod.io and place in user folder \AppData\Local\Larian Studios\Baldur's Gate 3\Mods~~
    - I have not published the mod currently

To make sure the changes are picked up, do a build and reload of the story

**BE SURE TO REMOVE SCRIPTS/FILES/DEPENDENCIES WHEN DONE TESTING AND BEFORE BUILDING PAK FILE**


## Usage
Guide on using the toolkit console: [Shortcuts & Commands for debugging](https://mod.io/g/baldursgate3/r/list-of-all-editor-hints-commands-shortcuts)


### Checks and Saving Throws

Command structure:  
`oe [check/save] [Skill/Ability Short/Full name] [DC] [Advantage/Disadvantage/Straight] [Active/Passive]`

- check/save
    - **Required**
    - Accepted values
        - `check`
        - `save`
    - For skills this does not appear to make a difference
    - For abilities this controls if an ability check or save is made
- Skill/Ability Short/Full name
    - **Required**
    - Accepted values
        - [See tables below](#short-names-and-full-names)
    - Determines which ability or skill to roll
- DC
    - Optional
        - Default value is `10` (DC10)
    - Accepted values
        - `0`
        - `5`
        - `10`
        - `15`
        - `20`
    - Sets DC of check or save
- Advantage/Disadvantage/Straight
    - Optional
        - Default is `0` (Straight Roll)
    - Accepted values
        - `-1` (Disadvantage)
        - `0` (Straight Roll)
        - `1` (Advantage)
    - Sets situational Advantage/Disadvange to leaves as Straight roll
- Active/Passive
    - Optional
        - Default value is `1` (Active)
    - Accepted values
        - `0` (Passive)
        - `1` (Active)
    - Controls if the roll is active (user can apply buffs, use insipration, etc) or passive


### short names and full names

Short name should be case insensitive, but if using the full name they must be exact

#### **Abilities**
| Short name     | Full name      |
| ---            | ---            |
| `str`          | `Strength`     |
| `dex`          | `Dexterity`    |
| `con`          | `Consitution`  |
| `int`          | `Intelligence` |
| `wis`          | `Wisdom`       |
| `chr`          | `Charisma`     |

#### **Skills**
| Short name       | Full name        |
| ---              | ---              |
| `acr`            | `Acrobatics`     |
| `ani`            | `AnimalHandling` |
| `arc`            | `Arcana`         |
| `ath`            | `Athletics`      |
| `dec`            | `Deception`      |
| `his`            | `History`        |
| `ins`            | `Insight`        |
| `itm`            | `Intimidation`   |
| `inv`            | `Investigation`  |
| `med`            | `Medicine`       |
| `pct`            | `Perception`     |
| `prf`            | `Performance`    |
| `psu`            | `Persuasion`     |
| `rel`            | `Religion`       |
| `sle`            | `SleightOfHand`  |
| `ste`            | `Stealth`        |
| `sur`            | `Survival`       |


### Spawning Treasure

Command structure:  
`oe treasure [Treasure Table] [Give to Avatar]`

- Treasure Table
    - **Required**
    - Accepted values
        - Needs to be a treasure table name (ex. `ST_GEN_Valuables_Jewelry_Gold`)
    - Controls item(s) that are generated
- Give to Avatar
    - Optional
        - Default is `0` (No)
    - Accepted values
        - `0` (No)
        - `1` (Yes)
    - Controls if the generated items are left in a container object at the avatars position, or placed into their inventory


### Spawning Creatures
WIP


## Other info
