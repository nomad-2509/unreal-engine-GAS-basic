# Gameplay Ability System

> Upto Chapter 4, **topic 4.2 - Gameplay Cues**

| Chapter |                                | Topics                         |                        |                    |
| ------- | ------------------------------ | ------------------------------ | ---------------------- | ------------------ |
| 1       | 1.1 - GAS & ASC initialize     | 1.2 - Attribute set            | 1.3 - Gameplay Effects |
| 2       | 2.1 - Melee implementation     | 2.2 - Melee Ability            | 2.3 - Block Ability    |
| 3       | 3.1 - Triple Jump              | 3.2 - Sprint Ability           | 3.3 - Dodge Ability    | 3.4 - Dash Ability |
| 4       | 4.1 - Disables - Silence, Stun | 4.2 - Gameplay Cues            | 4.3 - UI with GAS      |
| 5       | 5.1 - Blink + Ability Task     | 5.2 - Passive Ability          | 5.3 - Curve Table, MMC |
| 6       | 6.1 - Effect Execution Class   | 6.2 - Stacking and overflowing |

## Attributes and UI

-   Implemented
    -   Base attributes: Health, Mana, Stamina,
    -   Core attributes: Strength, Agility, Intelligence,
    -   Battle attributes: Armor, Movement Speed, Attack Speed etc.
-   Attribute widgets appear on HUD dynamically, when a pawn is possessed by player.

https://github.com/user-attachments/assets/37a4526d-9b6d-4cb0-b7d9-711f8a8db142

## Melee, Block and Parry

-   Parry window while blocking.
-   Blocking damages stamina, while parrying returns damage to source' stamina.

https://github.com/user-attachments/assets/c26436f9-406b-4d5c-a705-6e568df1457a

## Triple (or Quadruple) jump!

-   Any number of maximum jumps can be used, just by modifying an attribute.
-   Jump recharge effect occurs to refill number of jumps to maximum.
-   Also updating character walk speed in level based on a movement-speed attribute.

https://github.com/user-attachments/assets/086370fc-46e2-4558-be63-af96af9ee3aa

## Disable statuses

-   Implemented disable statuses from DotA 2 such as root, disarm, silence, stun etc.
-   Implemented using Gameplay Cues with appropriate animation across a multiplayer network.

https://github.com/user-attachments/assets/f2262a3f-d858-4bec-8d70-84b1cc476f1b

## Ability Target Data

-   Created an Asynchronous method (latent action) that can send a target data to server.
-   The ability sends the target data to server, and upon receiving, the appropriate ability action is performed.
-   So a player can blink to a target location that was set by local input values, and action will be performed by Server.

https://github.com/user-attachments/assets/df34e247-2593-45a6-b837-45f820561417

## Passive Ability & Break

-   Triggering a passive ability based on an event.
-   Break effect prevents the passive ability from activating.
-   Implemented Mana Burn from dota - notice how mana is damaged on melee hit, and when passive is disabled (break effect) mana burn does not happen.

https://github.com/user-attachments/assets/b6938b01-62c1-40f6-9902-f67fb207f2fd

## Curve Tables, Magnitude Modifier Calculation Class & Effect Execution Class

-   Utilized Curve Tables for Gameplay Effect values for a data-driven approach.
-   Used Magnitude Modifer Calculation Class for complex calculation of an effect modifier.
-   Also used Effect Execution Class to perform operation on a running effect.
    ![github-curve-table](https://github.com/user-attachments/assets/ea0e9939-b998-43d8-9d6d-183b637a6f2f)

## Meta Attributes, Stacking and Overflowing Effects

-   Health damaged/healed using a distinct meta-attribute.
-   Also refining the damage received through damage reduction from magical or physical damage, as in DotA 2.
-   Stacking an effect that overflows to perform another effect.

https://github.com/user-attachments/assets/959b067e-f186-46fc-b9a8-dcfcab85dc16
