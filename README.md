# bg3-tk-helper-scripts
 Helper scripts for testing in BG3 modding toolkit

## Contents
- [Setup Options](#setup-options)
- [Usage](#usage)
    - [Checks and Saving Throws](#checks-and-saving-throws)
    - [Spawning Treasure](#spawning-treasure)
    - [Spawning Creatures](#spawning-creatures)
- [Other Info](#other-info)


## Setup Options

1. Copy any script file(s) you want to use to `\Data\Mods\MODNAME_UUID\Story\RawFiles\Goals`
2. Copy the script contents into an existing osiris script for your mod
3. ~~Set the Util as a dependency from Project Settings. Either:~~
    - ~~Install from the in-game mod manager~~
    - ~~Download pak file from mod.io and place in user folder \AppData\Local\Larian Studios\Baldur's Gate 3\Mods~~
    - I have not published the mod currently

To make sure the changes are picked up, do a build and reload of the story

**BE SURE TO REMOVE SCRIPTS/FILES/DEPENDENCIES WHEN DONE TESTING AND BEFORE BUILDING PAK FILE**


## Usage
Guide on using the toolkit console: [Shortcuts & Commands for debugging](https://mod.io/g/baldursgate3/r/list-of-all-editor-hints-commands-shortcuts)

Several key things for using these scripts:
- Keeping the mouse over the console window prevents key presses triggering game inputs
- Page Up/Page Down cycle through commands
- The auto complete sometimes interferes with text event command, I use Shift+Space between parameters to avoid unwanted auto complete
- The prompt sometimes lags due to loading large auto complete lists.  Just give it a second


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
        - [See Abilities and Skills tables below](#short-names-and-full-names)
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
    - Sets situational Advantage/Disadvange or leaves as Straight roll
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

Command structure:
`oe spawn [Short name or GUID]`

- Short name or GUID
    - *Required*
    - Accepted values
        - Several short names are set up for basic spawns
            - [See Spawns table below]()
        - `Name_GUID` of for creature
    - Type of spawn to create


#### **Spawns**
| Short name      | GUID                                                                                |
| ---             | ---                                                                                 |
| `mage`          | `Humans_Male_FlamingFist_Caster_B_91392ba7-4a09-40f2-80c3-5410a165adaa`             |
| `melee`         | `Dwarves_Male_Hill_FlamingFist_Melee_Attacker_ff4900e5-ace9-4582-b1ca-dc144919f27d` |
| `ranged`        | `Humans_Female_FlamingFist_Ranger_B_ec34598b-0a16-4b50-b271-c6682893837f`           |
| `dino`          | `BASE_Dilophosaurus_ea400d0d-f3cc-4e12-b1a3-faf7e63e7780`                           |
| `undead`        | `Undead_DarkJusticiar_Boss_89419ac3-95d1-4c90-9a29-7b6445acb270`                    |


## Other info
