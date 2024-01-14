## Game Description

A basic Guitar Hero implementation for Hard Processor System (ARM Cortex A9) in DE1-SoC board. As in the real Guitar Hero game, notes are sliding down on the screen, and the player must push
the correct buttons, in the correct time (when the note overlaps with the button) in order to increase the score. Wrong button pushes decrease the score. The 4 push buttons on the DE1-SoC board
are used as buttons.

![guitar_hero_gameplay_ss](https://github.com/Mert-Yazgan/guitar_hero/assets/156585079/7a5195b6-27d8-417b-8a5b-bc686987d1d5)

Any push button can be pressed to start the game. A game run lasts 1.5 minutes (The original song in the code was 6 minutes 25 seconds but since I directly embedded the song data into the code,
with this size, it takes about 1.5 hours to upload the code to the DE1-SoC board so only the first 1.5 minutes of the song is taken so the game lasts 1.5 minutes.

![IMG-20240111-WA0000](https://github.com/Mert-Yazgan/guitar_hero/assets/156585079/84b1b7eb-9555-475a-8d3e-f735e93c72d7)

The flowchart below explains the game logic. Audio out port of the DE1-SoC board is used with interrupt for sound output, pixel buffer is used to display graphics (without double-buffering) and
character buffer is used to display the player score on the screen.

![game_flowchart](https://github.com/Mert-Yazgan/guitar_hero/assets/156585079/e60e7b12-b1f8-460e-bc3f-0d30563a278a)

## Instructions to play on CPUlator

The game can also be played from browser using CPUlator, which is a computer system simulator for DE1-SoC board. Only difference is that, since CPUlator allows source file sizes up to 12 MB,
instead of the 1.5 minutes long song data, a very short (about 5 seconds) sound sample is played continuously for 1.5 minutes. Also, as a mouse is used to click the push buttons on CPUlator,
unlike real hardware, it is not possible to press multiple buttons at the same time.

To play the game on CPUlator:

  1. Open https://cpulator.01xz.net/?sys=arm-de1soc&d_audio=48000
  2. Download the guitar_hero.c file from "CPUlator" branch (not main, which includes the code for the real hardware).
  3. Copy and paste the code on CPUlator and change the language from ARMv7 to C.
  4. Press Compile and Load. You may want to drag the VGA pixel buffer window to the top in order to easily see the screen while pressing push buttons.
  5. Press continue and start playing. Press any push button to start a new game run.

