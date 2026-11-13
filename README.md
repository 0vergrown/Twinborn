# Twinborn

Twinborn is a data pack with its resource pack built in. It adds the Twinborn origin to the Origins layer: two players bond as twins, trade strength, health and reach between them, breathe for each other and die together. Every power is built from Apoli JSON, with no commands and no Java.

This is a rebuild of InkBat's Twinborn origin for Apoli and Origins. The idea is InkBat's; the powers, menu art and text in this pack are new.

## Requirements

- Apoli 1.130.0 or newer and Origins 1.52.0 or newer
- Fabric 1.20.1, Fabric 1.21.1 or NeoForge 1.21.1

Put the folder (or a zip of it) in the world's `datapacks` folder and in your `resourcepacks` folder. The resource half carries the menu icons, the portrait frame, the red thread and all of the text.

## Bonding

A Twinborn needs a twin. Find another Twinborn, look at them from within 6 blocks, open the twin bond menu with the Origins primary key (G unless you changed it) and choose the heart in the middle. They get a message and have 30 seconds to do the same while looking at you. Once both of you have chosen, you are twins.

The bond lasts until one of you takes another origin. That also works while the other twin is offline: they find out the bond is broken when they next join.

## The twin bond menu

Every slice except the last two comes in a pair. The inner ring asks your twin for something and the outer ring gives it to them. A trade only happens when both of you choose the matching slices within 10 seconds of each other, so either twin can start it. Your twin sees a message with their own key binding, a short timer appears above their hunger bar, and when they open the menu the request waits for them as a gold button in the middle.

| Slice | Inner ring | Outer ring | One step |
|---|---|---|---|
| Top | Call your twin to your side | Go to your twin | Works across dimensions |
| Max Health | Ask for max health | Give max health | 2 hearts, from 2 to 18 hearts |
| Armor | Ask for armor | Give armor | 4 armor points, up to 16 either way |
| Attack Damage | Ask for attack damage | Give attack damage | 2 points, up to 8 either way |
| Attack Speed | Ask for attack speed | Give attack speed | 1 point, from 0 to 8 |
| Reach | Ask for reach | Give reach | Half a block, up to 2 blocks either way |
| Speed | Ask for speed | Give speed | A fifth of your speed, from 20% to 180% |
| Experience | Ask for a level | Give a level | One level |
| Bottom | Tie or cut the red thread | | |
| Upper left | Send items | | Items within 3 blocks of you |

Both twins start even, and whatever one of you gains the other loses. Hovering a slice shows exactly what the trade does, such as "You: 10 hearts now, 12 after". A slice you can't use right now is grey and says why: you already hold everything your twin can give, you have nothing left to give, or you need at least 4 armor points of your own before you can give armor away. When the bond breaks, both twins go back to even.

Sending items moves the items lying within 3 blocks of you to your twin's feet, in any of the three vanilla dimensions. In a dimension added by another mod it only works when both of you are in that dimension.

## Living as twins

Your twin's face sits in a small frame in the top left corner of your screen. It dims while they are offline and shows a knot while the red thread ties you. Hold sneak to see your twin glow through walls.

The red thread is 12 blocks long. Tying it needs both twins to choose it while standing within 12 blocks and in sight of each other. While it holds, it pulls back whichever of you strays too far, both of you can climb walls, and falls hurt half as much. Either twin can cut it from the menu without asking.

The Shared Blood power links your breath, food and effects. While you have full breath your twin can't drown, and the same goes for you. Food you eat feeds your twin a little. Potions you drink and the effects your food gives reach your twin too, and so do the poisons and other harmful effects creatures put on you when they hit you.

Never Alone is the drawback. While your twin is offline you can't move, build, break, attack or use items. You wait in a grey world, invisible and unhurt, until they come back. An Orb of Origin still works, so a player whose twin never returns can choose again. Whenever your twin dies, you die with them.

## Coming from InkBat's version

- The origin is `twinborn:twinborn` and every power uses the `twinborn` namespace. Old pairings and stats don't carry over.
- Pairing and trading go through the twin bond menu. Hotbar slots no longer pick the stat, and slot 9 no longer pairs.
- Reach uses `minecraft:player.block_interaction_range` and `minecraft:player.entity_interaction_range`, which Apoli also provides on 1.20.1, so Reach Entity Attributes isn't needed.
- The tether is now a real rope between the twins.
- Effects reach your twin when you drink, eat or get hit. Effects from beacons, conduits and splash potions stay with you.
- Your twin's food is topped up with one point and some saturation for every meal, where the old version handed out a full second of Saturation.

## Layout

Each visible power has a file named after it in `data/twinborn/powers/`, and everything that power uses sits in a folder of the same name: the menu, the twin set and the bond in `twin_bond/`, the stat resources and trades in `sharing/`, travel and item sending in `side_by_side/`, the rope in `red_thread/`, breath and effects in `shared_blood/`, and the limbo powers and the death link in `never_alone/`. The death message comes from the `twinborn:severed_bond` damage type. Textures live under `assets/twinborn/textures/`.
