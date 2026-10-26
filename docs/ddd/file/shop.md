# [Kingdom Hearts Dream Drop Distance](../index.md) - shop.bin

Location: `/item/jp/bin/`

Contains the data for command prices and availability in Moogle Shops.

Click a link below to jump to a specific section.
- [File Structure](#file-structure)
- [Entry Structure](#entry-structure)
	- [Moogle Shop](#moogle-shop)
	- [Medal Shop](#medal-shop)

## File Structure

| Amount | Description						|
|--------|----------------------------------|
| 1      | Header (12 bytes)				|
| X      | Entries (8 bytes each)			|
| 1      | EOF (CD CD CD CD)				|

## Entry Structure

`0x02` is each command's buying price. During Bargain Flurry, items can be bought for 80% of `0x02`. Items are sold back to the Moogle Shop for 50% of `0x02`. 

`0x04` is the Moogle Shop's required level for a given command. The Shop technically contains entries for practically all items, but only sell items based on the player's current shop level. There are 8 shop levels, and the shop levels up as you complete a World. Some items are marked higher than Level 8 (`0x04` = `63`); these are assumed to be unpurchasable.

`0x07` is not entirely known, but may be used as a distinction between the Moogle and Medal Shops.

| Position | Type	|	Description								|
|----------|--------|-------------------------------------------|
| 0x00     | int8	|	[Item Id](../dictionary/items)			|
| 0x01     | int8	|	[Item Category](../dictionary/items)	|
| 0x02     | int16	|	Buying Price							|
| 0x04     | int8	|	Shop Level								|
| 0x05     | int8	|	BLANK									|
| 0x06     | int8	|	Bargain-Exclusive flag					|
| 0x07     | int8	|	Shop Mode?								|

### Moogle Shop

The PC version includes recipes for Frootz Cat, Kab Kannon, R & R Seal, Beatalike, and Tubguin Ace. The 3DS file does not include these entries.

| Item (Hex) | Item ID | Item Category | Name                 | Price (Munny) | Shop Level | BLANK | Bargain-Exclusive | UNKNOWN |
|------------|---------|---------------|----------------------|---------------|------------|-------|-------------------|---------|
| 28         | 40      | 0             | Quick Blitz          | 100           | 1          | 0     | 0                 | 3       |
| 29         | 41      | 0             | Blizzard Edge        | 400           | 4          | 0     | 0                 | 3       |
| 2A         | 42      | 0             | Dark Break           | 1500          | 63         | 0     | 0                 | 1       |
| 2B         | 43      | 0             | Slot Edge            | 1200          | 63         | 0     | 0                 | 1       |
| 2C         | 44      | 0             | Blitz                | 1000          | 7          | 0     | 0                 | 3       |
| 2D         | 45      | 0             | Meteor Crash         | 2000          | 63         | 0     | 0                 | 1       |
| 2E         | 46      | 0             | Spark Dive           | 200           | 3          | 0     | 0                 | 3       |
| 2F         | 47      | 0             | Poison Dive          | 900           | 63         | 0     | 0                 | 1       |
| 30         | 48      | 0             | Drain Dive           | 100           | 63         | 0     | 0                 | 1       |
| 31         | 49      | 0             | Sliding Dash         | 150           | 1          | 0     | 1                 | 3       |
| 32         | 50      | 0             | Thunder Dash         | 600           | 5          | 0     | 1                 | 3       |
| 33         | 51      | 0             | Sonic Blade          | 2200          | 8          | 0     | 0                 | 3       |
| 34         | 52      | 0             | Dark Aura            | 2000          | 63         | 0     | 0                 | 1       |
| 35         | 53      | 0             | Zantetsuken          | 2000          | 63         | 0     | 0                 | 3       |
| 36         | 54      | 0             | Strike Raid          | 200           | 3          | 0     | 0                 | 3       |
| 37         | 55      | 0             | Spark Raid           | 1800          | 63         | 0     | 0                 | 1       |
| 38         | 56      | 0             | Circle Raid          | 1200          | 5          | 0     | 1                 | 3       |
| 39         | 57      | 0             | Aerial Slam          | 800           | 6          | 0     | 0                 | 3       |
| 3A         | 58      | 0             | Ars Arcanum          | 2400          | 63         | 0     | 0                 | 1       |
| 3B         | 59      | 0             | Dark Splicer         | 2400          | 63         | 0     | 0                 | 1       |
| 3C         | 60      | 0             | Gravity Strike       | 600           | 5          | 0     | 0                 | 3       |
| 3D         | 61      | 0             | Confusing Strike     | 400           | 4          | 0     | 0                 | 3       |
| 3E         | 62      | 0             | Tornado Strike       | 1500          | 7          | 0     | 0                 | 3       |
| 3F         | 63      | 0             | Prism Windmill       | 1500          | 8          | 0     | 1                 | 3       |
| 40         | 64      | 0             | Timestorm            | 800           | 6          | 0     | 0                 | 3       |
| 41         | 65      | 0             | Fire Windmill        | 600           | 63         | 0     | 0                 | 1       |
| 42         | 66      | 0             | Icebreaker           | 1000          | 8          | 0     | 0                 | 3       |
| 43         | 67      | 0             | Shadowbreaker        | 1800          | 7          | 0     | 0                 | 1       |
| 44         | 68      | 0             | Magnet Spiral        | 1800          | 8          | 0     | 1                 | 3       |
| 45         | 69      | 0             | Salvation            | 2400          | 8          | 0     | 0                 | 1       |
| 46         | 70      | 0             | Limit Storm          | 1500          | 63         | 0     | 0                 | 1       |
| 47         | 71      | 0             | Collision Magnet     | 1000          | 7          | 0     | 0                 | 3       |
| 48         | 72      | 0             | Sacrifice            | 1800          | 63         | 0     | 0                 | 1       |
| 49         | 73      | 0             | Break Time           | 1200          | 63         | 0     | 0                 | 1       |
| 4A         | 74      | 0             | Fire                 | 100           | 1          | 0     | 0                 | 3       |
| 4B         | 75      | 0             | Fira                 | 400           | 5          | 0     | 0                 | 3       |
| 4C         | 76      | 0             | Firaga               | 1000          | 7          | 0     | 0                 | 3       |
| 4D         | 77      | 0             | Dark Firaga          | 1800          | 63         | 0     | 0                 | 1       |
| 4E         | 78      | 0             | Firaga Burst         | 2000          | 63         | 0     | 0                 | 1       |
| 4F         | 79      | 0             | Mega Flare           | 2600          | 63         | 0     | 0                 | 1       |
| 50         | 80      | 0             | Blizzard             | 100           | 1          | 0     | 0                 | 3       |
| 51         | 81      | 0             | Blizzara             | 400           | 5          | 0     | 0                 | 3       |
| 52         | 82      | 0             | Blizzaga             | 1000          | 7          | 0     | 0                 | 3       |
| 53         | 83      | 0             | Icicle Splitter      | 700           | 63         | 0     | 0                 | 1       |
| 54         | 84      | 0             | Deep Freeze          | 1800          | 63         | 0     | 0                 | 1       |
| 55         | 85      | 0             | Ice Barrage          | 1500          | 63         | 0     | 0                 | 1       |
| 56         | 86      | 0             | Thunder              | 150           | 1          | 0     | 1                 | 3       |
| 57         | 87      | 0             | Thundara             | 600           | 5          | 0     | 1                 | 3       |
| 58         | 88      | 0             | Thundaga             | 1500          | 7          | 0     | 1                 | 3       |
| 59         | 89      | 0             | Triple Plasma        | 1500          | 63         | 0     | 0                 | 1       |
| 5A         | 90      | 0             | Cure                 | 100           | 2          | 0     | 0                 | 3       |
| 5B         | 91      | 0             | Cura                 | 600           | 6          | 0     | 0                 | 3       |
| 5C         | 92      | 0             | Curaga               | 1000          | 8          | 0     | 0                 | 3       |
| 5D         | 93      | 0             | Esuna                | 200           | 4          | 0     | 0                 | 3       |
| 5E         | 94      | 0             | Zero Gravity         | 200           | 3          | 0     | 0                 | 3       |
| 5F         | 95      | 0             | Zero Gravira         | 600           | 6          | 0     | 0                 | 3       |
| 60         | 96      | 0             | Zero Graviga         | 1000          | 8          | 0     | 0                 | 3       |
| 61         | 97      | 0             | Zero Graviza         | 1800          | 8          | 0     | 1                 | 3       |
| 62         | 98      | 0             | Balloon              | 300           | 1          | 0     | 1                 | 3       |
| 63         | 99      | 0             | Balloonra            | 900           | 5          | 0     | 1                 | 3       |
| 64         | 100     | 0             | Balloonga            | 1800          | 63         | 0     | 0                 | 1       |
| 65         | 101     | 0             | Spark                | 200           | 3          | 0     | 0                 | 3       |
| 66         | 102     | 0             | Sparkra              | 800           | 6          | 0     | 0                 | 3       |
| 67         | 103     | 0             | Sparkga              | 2000          | 8          | 0     | 1                 | 3       |
| 68         | 104     | 0             | Faith                | 2400          | 63         | 0     | 0                 | 1       |
| 69         | 105     | 0             | Tornado              | 2000          | 63         | 0     | 0                 | 1       |
| 6A         | 106     | 0             | Meteor               | 2600          | 63         | 0     | 0                 | 1       |
| 6B         | 107     | 0             | Mini                 | 600           | 63         | 0     | 0                 | 1       |
| 6C         | 108     | 0             | Blackout             | 400           | 63         | 0     | 0                 | 1       |
| 6D         | 109     | 0             | Time Bomb            | 450           | 1          | 0     | 1                 | 3       |
| 6E         | 110     | 0             | Confuse              | 200           | 2          | 0     | 0                 | 3       |
| 6F         | 111     | 0             | Bind                 | 400           | 4          | 0     | 0                 | 3       |
| 70         | 112     | 0             | Poison               | 400           | 3          | 0     | 0                 | 3       |
| 71         | 113     | 0             | Slow                 | 200           | 2          | 0     | 0                 | 3       |
| 72         | 114     | 0             | Sleep                | 100           | 1          | 0     | 0                 | 3       |
| 73         | 115     | 0             | Sleepra              | 300           | 5          | 0     | 0                 | 3       |
| 74         | 116     | 0             | Sleepga              | 600           | 63         | 0     | 0                 | 1       |
| 75         | 117     | 0             | Stop                 | 600           | 63         | 0     | 0                 | 1       |
| 76         | 118     | 0             | Vanish               | 1800          | 63         | 0     | 0                 | 1       |
| 77         | 119     | 0             | Potion               | 20            | 1          | 0     | 0                 | 3       |
| 78         | 120     | 0             | Hi-Potion            | 40            | 2          | 0     | 0                 | 3       |
| 79         | 121     | 0             | Mega-Potion          | 100           | 5          | 0     | 0                 | 3       |
| 7A         | 122     | 0             | Drop-Me-Not          | 40            | 2          | 0     | 0                 | 3       |
| 7B         | 123     | 0             | Drop-Me-Never        | 240           | 63         | 0     | 0                 | 1       |
| 7C         | 124     | 0             | Panacea              | 50            | 2          | 0     | 0                 | 3       |
| 7D         | 125     | 0             | Elixir               | 3000          | 1          | 0     | 1                 | 3       |
| 7E         | 126     | 0             | Megalixir            | 4000          | 63         | 0     | 0                 | 1       |
| 7F         | 127     | 0             | Dream Candy          | 400           | 63         | 0     | 0                 | 1       |
| 02         | 2       | 0             | High Jump            | 100           | 63         | 0     | 0                 | 1       |
| 04         | 4       | 0             | Slide Roll           | 400           | 63         | 0     | 0                 | 1       |
| 05         | 5       | 0             | Dark Roll            | 400           | 63         | 0     | 0                 | 1       |
| 07         | 7       | 0             | Sonic Impact         | 300           | 5          | 0     | 0                 | 3       |
| 08         | 8       | 0             | Double Impact        | 300           | 63         | 0     | 0                 | 1       |
| 0A         | 10      | 0             | Super Glide          | 400           | 63         | 0     | 0                 | 1       |
| 0B         | 11      | 0             | Shadow Slide         | 500           | 63         | 0     | 0                 | 1       |
| 0C         | 12      | 0             | Doubleflight         | 400           | 63         | 0     | 0                 | 1       |
| 0E         | 14      | 0             | Wake-Up Block        | 400           | 6          | 0     | 0                 | 3       |
| 0F         | 15      | 0             | Link Block           | 500           | 8          | 0     | 0                 | 3       |
| 10         | 16      | 0             | Sliding Block        | 400           | 63         | 0     | 0                 | 1       |
| 11         | 17      | 0             | Dark Barrier         | 500           | 63         | 0     | 0                 | 1       |
| 12         | 18      | 0             | Counter Rush         | 300           | 63         | 0     | 0                 | 1       |
| 13         | 19      | 0             | Counter Aura         | 400           | 6          | 0     | 0                 | 3       |
| 14         | 20      | 0             | Shadow Strike        | 500           | 63         | 0     | 0                 | 1       |
| 15         | 21      | 0             | Payback Raid         | 400           | 7          | 0     | 0                 | 3       |
| 16         | 22      | 0             | Payback Blast        | 400           | 7          | 0     | 0                 | 3       |
| 17         | 23      | 0             | Aerial Recovery      | 400           | 6          | 0     | 0                 | 3       |
| 18         | 24      | 0             | Steep Climb          | 400           | 63         | 0     | 0                 | 1       |
| 19         | 25      | 0             | Rapid Descent        | 400           | 63         | 0     | 0                 | 1       |
| 1A         | 26      | 0             | Sliding Sidewinder   | 400           | 7          | 0     | 0                 | 3       |
| 1B         | 27      | 0             | Sliding Crescent     | 400           | 7          | 0     | 0                 | 3       |
| 00         | 0       | 6             | Fleeting Figment     | 150           | 4          | 0     | 0                 | 3       |
| 01         | 1       | 6             | Fleeting Fancy       | 300           | 7          | 0     | 0                 | 3       |
| 02         | 2       | 6             | Fleeting Fantasy     | 1000          | 7          | 0     | 1                 | 3       |
| 03         | 3       | 6             | Lofty Figment        | 100           | 3          | 0     | 0                 | 3       |
| 04         | 4       | 6             | Lofty Fancy          | 400           | 8          | 0     | 0                 | 3       |
| 05         | 5       | 6             | Lofty Fantasy        | 800           | 63         | 0     | 0                 | 1       |
| 06         | 6       | 6             | Rampant Figment      | 50            | 1          | 0     | 0                 | 3       |
| 07         | 7       | 6             | Rampant Fancy        | 200           | 5          | 0     | 0                 | 3       |
| 08         | 8       | 6             | Rampant Fantasy      | 500           | 1          | 0     | 1                 | 3       |
| 09         | 9       | 6             | Dulcet Figment       | 100           | 3          | 0     | 0                 | 3       |
| 0A         | 10      | 6             | Dulcet Fancy         | 400           | 8          | 0     | 0                 | 3       |
| 0B         | 11      | 6             | Dulcet Fantasy       | 1000          | 8          | 0     | 1                 | 3       |
| 0C         | 12      | 6             | Malleable Fantasy    | 2000          | 63         | 0     | 0                 | 1       |
| 0D         | 13      | 6             | Prickly Fantasy      | 2000          | 63         | 0     | 0                 | 1       |
| 0E         | 14      | 6             | Wild Fantasy         | 2000          | 63         | 0     | 0                 | 1       |
| 0F         | 15      | 6             | Epic Fantasy         | 2000          | 63         | 0     | 0                 | 1       |
| 10         | 16      | 6             | Charming Fantasy     | 2000          | 63         | 0     | 0                 | 1       |
| 11         | 17      | 6             | Brilliant Fantasy    | 2000          | 63         | 0     | 0                 | 1       |
| 12         | 18      | 6             | Intrepid Figment     | 50            | 2          | 0     | 0                 | 3       |
| 13         | 19      | 6             | Intrepid Fancy       | 400           | 8          | 0     | 0                 | 3       |
| 14         | 20      | 6             | Intrepid Fantasy     | 1000          | 8          | 0     | 1                 | 3       |
| 15         | 21      | 6             | Savage Fantasy       | 2000          | 8          | 0     | 0                 | 3       |
| 16         | 22      | 6             | Noble Figment        | 100           | 3          | 0     | 0                 | 3       |
| 17         | 23      | 6             | Noble Fancy          | 200           | 5          | 0     | 0                 | 3       |
| 18         | 24      | 6             | Noble Fantasy        | 800           | 3          | 0     | 1                 | 3       |
| 19         | 25      | 6             | Grim Figment         | 50            | 2          | 0     | 0                 | 3       |
| 1A         | 26      | 6             | Grim Fancy           | 300           | 7          | 0     | 0                 | 3       |
| 1B         | 27      | 6             | Grim Fantasy         | 300           | 7          | 0     | 0                 | 3       |
| 1C         | 28      | 6             | Vibrant Figment      | 50            | 1          | 0     | 0                 | 3       |
| 1D         | 29      | 6             | Vibrant Fancy        | 200           | 5          | 0     | 0                 | 3       |
| 1E         | 30      | 6             | Vibrant Fantasy      | 500           | 2          | 0     | 1                 | 3       |
| 1F         | 31      | 6             | Troubling Figment    | 50            | 1          | 0     | 0                 | 3       |
| 20         | 32      | 6             | Troubling Fancy      | 100           | 3          | 0     | 0                 | 3       |
| 21         | 33      | 6             | Troubling Fantasy    | 500           | 2          | 0     | 1                 | 3       |
| 22         | 34      | 6             | Wondrous Figment     | 150           | 4          | 0     | 0                 | 3       |
| 23         | 35      | 6             | Wondrous Fancy       | 300           | 7          | 0     | 0                 | 3       |
| 24         | 36      | 6             | Wondrous Fantasy     | 400           | 8          | 0     | 0                 | 3       |
| 01         | 1       | 3             | Tama Sheep Recipe    | 50            | 3          | 0     | 0                 | 2       |
| 04         | 4       | 3             | Pricklemane Recipe   | 50            | 1          | 0     | 0                 | 2       |
| 05         | 5       | 3             | Hebby Repp Recipe    | 50            | 1          | 0     | 0                 | 2       |
| 08         | 8       | 3             | Fin Fatale Recipe    | 100           | 2          | 0     | 0                 | 2       |
| 0A         | 10      | 3             | Necho Cat Recipe     | 200           | 4          | 0     | 0                 | 2       |
| 0E         | 14      | 3             | Iceguin Ace Recipe   | 200           | 6          | 0     | 0                 | 2       |
| 10         | 16      | 3             | Escarglow Recipe     | 100           | 3          | 0     | 0                 | 2       |
| 11         | 17      | 3             | KO Kabuto Recipe     | 200           | 4          | 0     | 0                 | 2       |
| 16         | 22      | 3             | Halbird Recipe       | 300           | 7          | 0     | 0                 | 2       |
| 18         | 24      | 3             | Fishboné Recipe      | 100           | 5          | 0     | 0                 | 2       |
| 19         | 25      | 3             | Flowbermeow Recipe   | 1000          | 63         | 0     | 1                 | 2       |
| 1D         | 29      | 3             | Tatsu Blaze Recipe   | 100           | 5          | 0     | 0                 | 2       |
| 1F         | 31      | 3             | Woeflower Recipe     | 200           | 3          | 0     | 0                 | 2       |
| 22         | 34      | 3             | Me Me Bunny Recipe   | 100           | 6          | 0     | 0                 | 2       |
| 29         | 41      | 3             | Aura Lion Recipe     | 500           | 8          | 0     | 0                 | 2       |
| 2F         | 47      | 3             | Frootz Cat Recipe    | 500           | 7          | 0     | 0                 | 2       |
| 31         | 49      | 3             | Kab Kannon Recipe    | 500           | 7          | 0     | 0                 | 2       |
| 32         | 50      | 3             | R & R Seal Recipe    | 200           | 2          | 0     | 0                 | 2       |
| 34         | 52      | 3             | Beatalike Recipe     | 1000          | 8          | 0     | 0                 | 2       |
| 35         | 53      | 3             | Tubguin Ace Recipe   | 200           | 2          | 0     | 0                 | 2       |
| 00         | 0       | 7             | Confetti Candy       | 30            | 1          | 0     | 0                 | 3       |
| 01         | 1       | 7             | Shield Cookie        | 30            | 1          | 0     | 0                 | 3       |
| 02         | 2       | 7             | Block-It Chocolate   | 30            | 1          | 0     | 0                 | 3       |
| 03         | 3       | 7             | Ice Dream Cone       | 30            | 1          | 0     | 0                 | 3       |
| 04         | 4       | 7             | Royal Cake           | 240           | 1          | 0     | 0                 | 1       |
| 05         | 5       | 7             | Confetti Candy 2     | 120           | 4          | 0     | 0                 | 3       |
| 06         | 6       | 7             | Shield Cookie 2      | 120           | 4          | 0     | 0                 | 3       |
| 07         | 7       | 7             | Block-It Chocolate 2 | 120           | 4          | 0     | 0                 | 3       |
| 08         | 8       | 7             | Ice Dream Cone 2     | 120           | 4          | 0     | 0                 | 3       |
| 0A         | 10      | 7             | Confetti Candy 3     | 240           | 7          | 0     | 1                 | 3       |
| 0B         | 11      | 7             | Shield Cookie 3      | 240           | 7          | 0     | 1                 | 3       |
| 0C         | 12      | 7             | Block-It Chocolate 3 | 240           | 7          | 0     | 1                 | 3       |
| 0D         | 13      | 7             | Ice Dream Cone 3     | 240           | 7          | 0     | 1                 | 3       |
| 00         | 0       | 8             | Balloon              | 80            | 1          | 0     | 0                 | 3       |
| 03         | 3       | 8             | Candy Goggles        | 80            | 1          | 0     | 0                 | 3       |
| 04         | 4       | 8             | Water Barrel         | 80            | 1          | 0     | 0                 | 3       |
| 05         | 5       | 8             | Paint Gun: Red       | 10            | 1          | 0     | 0                 | 3       |
| 06         | 6       | 8             | Paint Gun: Blue      | 10            | 1          | 0     | 0                 | 3       |
| 07         | 7       | 8             | Paint Gun: Green     | 10            | 1          | 0     | 0                 | 3       |
| 08         | 8       | 8             | Paint Gun: Yellow    | 10            | 1          | 0     | 0                 | 3       |
| 09         | 9       | 8             | Paint Gun: White     | 10            | 1          | 0     | 0                 | 3       |
| 0A         | 10      | 8             | Paint Gun: Black     | 10            | 1          | 0     | 0                 | 3       |
| 0B         | 11      | 8             | Paint Gun: Purple    | 10            | 1          | 0     | 0                 | 3       |
| 0C         | 12      | 8             | Paint Gun: Sky Blue  | 10            | 1          | 0     | 0                 | 3       |


### Medal Shop

Medal Shops begin at offset `05B0` on PC, and can otherwise be distinguished by `0x07` = `00`.

| Item (Hex) | Item ID | Item Category | Name                 | Price (Medals) | Shop Level | BLANK | Bargain-Exclusive | Mode    |
|------------|---------|---------------|----------------------|----------------|------------|-------|-------------------|---------|
| 2B         | 43      | 0             | Slot Edge            | 150            | 1          | 0     | 0                 | 0       |
| 30         | 48      | 0             | Drain Dive           | 120            | 1          | 0     | 0                 | 0       |
| 41         | 65      | 0             | Fire Windmill        | 250            | 1          | 0     | 0                 | 0       |
| 46         | 70      | 0             | Limit Storm          | 1000           | 5          | 0     | 0                 | 0       |
| 48         | 72      | 0             | Sacrifice            | 1000           | 5          | 0     | 0                 | 0       |
| 4E         | 78      | 0             | Firaga Burst         | 2000           | 8          | 0     | 0                 | 0       |
| 54         | 84      | 0             | Deep Freeze          | 1200           | 5          | 0     | 0                 | 0       |
| 59         | 89      | 0             | Triple Plasma        | 1500           | 8          | 0     | 0                 | 0       |
| 64         | 100     | 0             | Balloonga            | 1200           | 5          | 0     | 0                 | 0       |
| 6B         | 107     | 0             | Mini                 | 200            | 1          | 0     | 0                 | 0       |
| 75         | 117     | 0             | Stop                 | 150            | 1          | 0     | 0                 | 0       |
| 7B         | 123     | 0             | Drop-Me-Never        | 100            | 5          | 0     | 0                 | 0       |
| 7E         | 126     | 0             | Megalixir            | 4000           | 8          | 0     | 0                 | 0       |
| 7F         | 127     | 0             | Dream Candy          | 200            | 1          | 0     | 0                 | 0       |
| 05         | 5       | 0             | Dark Roll            | 700            | 8          | 0     | 0                 | 0       |
| 11         | 17      | 0             | Dark Barrier         | 750            | 8          | 0     | 0                 | 0       |
| 0B         | 11      | 3             | Thunderaffe Recipe   | 280            | 4          | 0     | 0                 | 0       |
| 0C         | 12      | 3             | Kooma Panda Recipe   | 80             | 0          | 0     | 0                 | 0       |
| 0D         | 13      | 3             | Pegaslick Recipe     | 330            | 5          | 0     | 0                 | 0       |
| 15         | 21      | 3             | Juggle Pup Recipe    | 180            | 2          | 0     | 0                 | 0       |
| 23         | 35      | 3             | Drill Sye Recipe     | 150            | 1          | 0     | 0                 | 0       |
| 25         | 37      | 3             | Majik Lapin Recipe   | 400            | 6          | 0     | 0                 | 0       |
| 2D         | 45      | 3             | Meowjesty Recipe     | 2000           | 5          | 14    | 0                 | 0       |
| 2E         | 46      | 3             | Sudo Neku Recipe     | 2000           | 4          | 14    | 0                 | 0       |
| 30         | 48      | 3             | Ursa Circus Recipe   | 2000           | 7          | 14    | 0                 | 0       |
| 00         | 0       | 7             | Confetti Candy       | 40             | 1          | 0     | 0                 | 0       |
| 01         | 1       | 7             | Shield Cookie        | 40             | 1          | 0     | 0                 | 0       |
| 02         | 2       | 7             | Block-It Chocolate   | 40             | 1          | 0     | 0                 | 0       |
| 03         | 3       | 7             | Ice Dream Cone       | 40             | 1          | 0     | 0                 | 0       |
| 04         | 4       | 7             | Royal Cake           | 300            | 8          | 0     | 0                 | 0       |
| 05         | 5       | 7             | Confetti Candy 2     | 100            | 4          | 0     | 0                 | 0       |
| 06         | 6       | 7             | Shield Cookie 2      | 100            | 4          | 0     | 0                 | 0       |
| 07         | 7       | 7             | Block-It Chocolate 2 | 100            | 4          | 0     | 0                 | 0       |
| 08         | 8       | 7             | Ice Dream Cone 2     | 100            | 4          | 0     | 0                 | 0       |
| 0A         | 10      | 7             | Confetti Candy 3     | 200            | 7          | 0     | 0                 | 0       |
| 0B         | 11      | 7             | Shield Cookie 3      | 200            | 7          | 0     | 0                 | 0       |
| 0C         | 12      | 7             | Block-It Chocolate 3 | 200            | 7          | 0     | 0                 | 0       |
| 0D         | 13      | 7             | Ice Dream Cone 3     | 200            | 7          | 0     | 0                 | 0       |
| 00         | 0       | 8             | Balloon              | 50             | 1          | 0     | 0                 | 0       |
| 03         | 3       | 8             | Candy Goggles        | 50             | 1          | 0     | 0                 | 0       |
| 04         | 4       | 8             | Water Barrel         | 50             | 1          | 0     | 0                 | 0       |
| 05         | 5       | 8             | Paint Gun: Red       | 5              | 1          | 0     | 0                 | 0       |
| 06         | 6       | 8             | Paint Gun: Blue      | 5              | 1          | 0     | 0                 | 0       |
| 07         | 7       | 8             | Paint Gun: Green     | 5              | 1          | 0     | 0                 | 0       |
| 08         | 8       | 8             | Paint Gun: Yellow    | 5              | 1          | 0     | 0                 | 0       |
| 09         | 9       | 8             | Paint Gun: White     | 5              | 1          | 0     | 0                 | 0       |
| 0A         | 10      | 8             | Paint Gun: Black     | 5              | 1          | 0     | 0                 | 0       |
| 0B         | 11      | 8             | Paint Gun: Purple    | 5              | 1          | 0     | 0                 | 0       |
| 0C         | 12      | 8             | Paint Gun: Sky Blue  | 5              | 1          | 0     | 0                 | 0       |
