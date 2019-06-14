# digital-record-player

This repo contains code and [instructions](HOWTO.md) for converting a record player into a sort of personal jukebox.

The Digital Record Player is an object that looks outwardly like a record player, with the exception of a small numerical keypad and an LCD. The user enters a numerical code on the keypad and presses Enter. Then, they place a record on the turntable and drop the needle onto it. A few seconds later, the album they selected starts playing. After the first side of the album has finished, the user moves the needle back to the edge of the record (optionally flipping it over first) and plays the second side.

### How does it work?

Inside the record player is a Raspberry Pi. The keypad and LCD are both connected to this RPi, as is the record player's audio jack. The RPi draws power from the same power source as the record player. The RPi is also rigged up in such a way that it can detect whether the turntable is spinning.

Some number of albums have been loaded onto the RPi's persistent storage card, in MP3 format. Each of these albums has a corresponding number. When the user enters a number and presses Enter, the RPi registers their choice. Then, when it detects that the turntable has started spinning, the RPi waits some number of seconds (to simulate the moment when the needle is moving across the **lead-in** – the unrecorded ring around the edge of the record) and begins playing the album.
