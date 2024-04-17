# GB-Studio-Examples
Example videos and roms for GBS concepts

# Text Entry
Two ways of doing text entry as well as using the same variables to impact other things like stats. There are no strings so each character's [ascii value](https://www.asciitable.com/) has to be stored to a variable each, meaning when you call the name in dialog, you have to call all the variables one after the other using # instead of $. I edited the font files to replace the @ symbol (ascii char 64) to just be empty using the magenta color designed for variable width fonts so if there is an empty character, it gives the illusion that the name is shorter insead of making a bunch of switch cases.
![gbs-var](https://github.com/dochardware/GB-Studio-Examples/assets/1316677/78041a48-8fef-4931-a5d7-e12c4ff3e06d)



## Keyboard
[Text Entry 1 - ROM Download](https://github.com/dochardware/GB-Studio-Examples/blob/main/TextEntry_V1.gb)

https://github.com/dochardware/GB-Studio-Examples/assets/1316677/60af7f73-48ae-4287-8da7-21d82c43f346

This one uses the Get Tile ID plugin to pull the unique tile id that the player/cursor is currently on top of and stored to a variable, then a value is added to the variable so it matches the ascii value of that character. The tricky part here is that *all* the background tiles have different IDs except where they're identical so in order to make this work, you'd have to check the id's of your letter tiles at the beginning of each row, then adjust how much is added to the variable based on what row the player is on.

As a little treat, the variables are also used to generate a profile id. Characters 1 - 4 are stats and character 5 is the profile image.

You could also just use triggers for this style of entry but if you plan on having more than 30 characters, then you'd have to figure out some kinda way to switch the outcomes.


## Slots
[Text Entry 2 - ROM Download](https://github.com/dochardware/GB-Studio-Examples/blob/main/TextEntry_V2.gb)

https://github.com/dochardware/GB-Studio-Examples/assets/1316677/83470b30-fcee-401c-b4b9-3c53648c3f39

This is a lot easier since it uses sprites for the letters and triggers for the controls. Variable value is pulled from the current frame of the corresponding sprite then 64 is added to adjust to the correct ascii value. 

![Feel free to use this spritesheet](https://github.com/dochardware/GB-Studio-Examples/assets/1316677/aa6cf2e0-7971-41eb-9539-fdb103553385)
