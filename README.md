# More Freeplay Difficulties

Adds more fun difficulties for players to play and modders and charters to use!
This mod includes **Insane**, **Duet**, **Chill**, **Edit**, **4K**, **7K**.
[Here's an example mod that uses this mod!][def]

## But I want to add my custom difficulty to base game too!

### Here's how

for assets you need:

- the chart files with your custom difficulties in them.
- You need `freeplay<diffId>` in `images/freeplay` and `diff_<diffId>` in `shared/images/resultScreen`.<br><br>
For the former, letters aren't exactly the same in the game (the A in `freeplayhard` doesn't look like the same as A in `freeplayeasy`) meaning you can't make a font, so you have to handdraw the difficulty yourself.<br><br>
For the latter, you can open [the letters' flash file](https://github.com/FunkinCrew/funkin.art/blob/66572f85d826ce2ec1d45468c12733b161237ffa/flashFiles/TARDLING%20FONT%20ALL.ana) with the required software (Adobe Animate 2022 worked for me), once you have colored the letter, export it as a png sequence, hence and repeat for your required difficulty letters. (once you're done with the word, don't forget to change the angle to **-4.4 degree**)

### and that's it, but wait!

You may encounter [this bug](https://github.com/FunkinCrew/Funkin/issues/3912), here's the method to fix it using this mod:
The simplest and most efficient way of doing it is by [making a JSON patch that adds your new difficulty into the json file](https://funkincrew.github.io/funkin-modding-docs/10-appending-and-merging-files/10-02-merging-files.html#merging-into-json-files) without affecting base game or other mods.

Again, It is **strongly** recommended to use `_merge` logic to avoid compatibility issues with mods!

- Add a file called `extraDiffs.json` in `yourmod/_merge/data`
- The rest is simple if you read [the documentation linked above](https://funkincrew.github.io/funkin-modding-docs/10-appending-and-merging-files/10-02-merging-files.html#merging-into-json-files), but here's a snippet if you want a quick copy & paste.

```json
[
{
    "op": "add",
    "path": "/difficulties/-",
    "value": {
        "id": "mania",
        "x": -10
    }
}
]
```

`id` is self explanatory, `x` and `y` are optional values and control the placement of the difficulty sprite in freeplay menu in case your sprite is off center.


[def]: https://gamebanana.com/mods/573160
