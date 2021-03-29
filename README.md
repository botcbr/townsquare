# Blood on the Clocktower Grimoire & Town Square

![social](https://user-images.githubusercontent.com/325521/102897760-d1147b00-4468-11eb-9d7b-63a204bc9fc1.png)

This is an unofficial online tool to run Blood on the Clocktower games through Discord or other digital means.
It is supposed to aid storytellers and players by allowing them to quickly set up games, run votes and much more.

[You can try it online!](https://clocktower.online)

If you want to learn more about how to use the app as a player, [JayBotC](https://www.youtube.com/channel/UCNZy-4Rp877XtTHaIZdWYFQ) kindly created two tutorial videos.

### How to host a game
[![How to host a game](https://img.youtube.com/vi/lVRJPBXfqxg/0.jpg)](https://www.youtube.com/watch?v=lVRJPBXfqxg)

### How to play a game
[![How to play a game](https://img.youtube.com/vi/VCpFnJFiCbk/0.jpg)](https://www.youtube.com/watch?v=VCpFnJFiCbk)

## Features

- Public Town Square and Storyteller Grimoire (toggle with **shortcut \[G\]**)
- Supports custom script JSON generated by the [Script Tool](https://bloodontheclocktower.com/script)
- Live Session for Storyteller / Players including live voting and character distribution!
- Includes all 3 base editions, Travelers and Fabled plus all officially spoiled characters so far!
- Night sheet and reminder text for each character ability to help storytellers
- Full homebrew support for hosting and playing games with your own sets of characters
- Many other customization options!

### Custom Script Support

Any custom script generated by the official [Script Tool](https://bloodontheclocktower.com/script) is supported out of
the box and you only need to upload it to get the selected set of characters into your grimoire. If you want to customize
your script further, there is an additional `"_meta"` object that you can add to the script like you would add a normal
character:

```json
[
  {
    "id": "_meta",
    "name": "Deadly Penance Day",
    "author": "TPI",
    "logo": "https://url.to/your/logo.png"
  }
]
```

This will provide your local Grimoire (and those of your live session players) with more information to show about
your custom script - instead of "Custom Script" it would show "Deadly Penance Day" on the character reference sheet,
for example. The logo will be shown to your players after they have enabled custom images in the Grimoire menu.

### Custom Character Support

In order to add custom characters to your local Grimoire, you need to create a JSON definition for them,
similar to what is provided in the [`roles.json`](https://github.com/bra1n/townsquare/blob/main/src/roles.json) for the 3 base editions. Here's an example of how such a character
definition file might be written:

```json
[
  {
    "id": "acrobat",
    "image": "https://github.com/bra1n/townsquare/blob/main/src/assets/icons/acrobat.png?raw=true",
    "edition": "custom",
    "firstNight": 0,
    "firstNightReminder": "",
    "otherNight": 49,
    "otherNightReminder": "If either good living neighbor is drunk or poisoned, the Acrobat dies.",
    "reminders": ["Die"],
    "remindersGlobal": [],
    "setup": false,
    "name": "Acrobat",
    "team": "outsider",
    "ability": "Each night*, if either good living neighbor is drunk or poisoned, you die."
  },
  { 
    "id": "investigator" 
  },
  { 
    "id": "imp" 
  }
]
```

This definition JSON includes a custom character, the Acrobat, and 2 base game characters, the Investigator and the Imp.
For base game characters, it is sufficient to only provide the ID, similar to what you get from the Script Tool.

**Required properties:** `id`, `name`, `team`, `ability`

- **id**: the internal ID for this character, without spaces or special characters<br>
  _Note_: this ID needs to be unique and can't be the same as any ID already used by an existing character, otherwise the custom character will be overwritten with the existing role!
- **image**: a URL to a PNG of the character token icon (should have a transparent background!)<br>
  _Note_: custom images will only be visible after enabling them in the Grimoire menu!
- **edition**: the ID of the edition for this character. can be left blank or "custom"
- **firstNight** / **otherNight**: the position that this character acts on the first / other nights, compared to all
  other characters
- **firstNightReminder** / **otherNightReminder**: reminder text for first / other nights
- **reminders**: reminder tokens, should be an empty array `[]` if none
- **remindersGlobal**: global reminder tokens that will always be available, no matter if the character is assigned to a player or not
- **setup**: whether this token affects setup (orange leaf), like the Drunk or Baron
- **name**: the displayed name of this character
- **team**: the team of the character, has to be one of `townsfolk`, `outsider`, `minion`, `demon` or `traveler`
- **ability**: the displayed ability text of the character

## [Code of Conduct](CODE_OF_CONDUCT.md)

## [Contributing](CONTRIBUTING.md)

## Acknowledgements and Copyrights

* [Blood on the Clocktower](https://bloodontheclocktower.com/) is a trademark of Steven Medway and [The Pandemonium Institute](https://www.thepandemoniuminstitute.com/)
* Night reminders and other auxiliary text written by [Ben Finney](http://bignose.whitetree.org/projects/botc/diy/)
* Iconography by [Font Awesome](https://fontawesome.com/)
* Background image by [Ryan Maloney](https://www.artstation.com/maloney94)
* Webfonts by [Google Fonts](https://fonts.google.com/) and [Online Web Fonts](https://www.onlinewebfonts.com/)
* All other images and icons are copyright to their respective owners

This project and its website are provided free of charge and not affiliated with The Pandemonium Institute in any way.

## Donations
This project will always be available free of charge, since I love building cool things and playing Blood on the Clocktower. If you still want to support me with a donation, you can do that here:

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/bra1n)
