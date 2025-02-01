# More Freeplay Difficulties

Adds more fun difficulties for players to play and modders and charters to use!
This mod includes **Insane**, **Duet**, **Chill**, **Edit**, **4K**, **7K**.
[Here's an example mod that uses this mod! (add GB link)]

## But I want to add my custom difficulty to base game too!

### Here's how

First [add this mod as a dependency](https://funkincrew.github.io/funkin-modding-docs/01-fundamentals/01-01-the-metadata-file.html)
for assets you need:

- the chart files with your custom difficulties in them ([Here's an example mod that uses this mod for Insane and Duet difficulties]).
- You need `freeplay<diffId>` in `images/freeplay` and `diff_<diffId>` in `shared/images/resultScreen`.<br><br>
For the former, letters aren't exactly the same in the game (the A in `freeplayhard` doesn't look like the same as A in `freeplayeasy`) meaning you can't make a font, so you have to handdraw the difficulty yourself.<br><br>
For the latter, you can open [the letters' flash file](https://github.com/FunkinCrew/funkin.art/blob/66572f85d826ce2ec1d45468c12733b161237ffa/flashFiles/TARDLING%20FONT%20ALL.ana) with the required software (Adobe Animate 2022 worked for me), once you have colored the letter, export it as a png sequence, hence and repeat for your required difficulty letters. (once you're done with the word, don't forget to change the angle to **-4.4 degree**)

### and that's it, but wait!

You may encounter [this bug](https://github.com/FunkinCrew/Funkin/issues/3912), here's the method to fix it using this mod:
The simplest method that worked for me is [appending the JSON file that stores all extra difficulties](https://funkincrew.github.io/funkin-modding-docs/10-appending-and-merging-files/10-01-appending-files.html#appending-to-json-files).
- Add a file called `extraDiffs.json` in `yourmod/_append/data`
- The rest is simple if you read [the documentation linked above](https://funkincrew.github.io/funkin-modding-docs/10-appending-and-merging-files/10-01-appending-files.html#appending-to-json-files). simple as that but here's an example snippet to make things quicker.

```json
{
    "difficulties": [
        {"id": "duet", "x": -9}
    ]
}
```

`id` is self explanatory, `x` and `y` are optional values and control the placement of the difficulty sprite in freeplay menu in case your sprite is off center. 
