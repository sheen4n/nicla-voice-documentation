# Nicla Voice Documentation

## Purpose

This serves as a guide to help people who wish to setup Nicla Voice, for audio recording and processing purposes.

## Setting up Nicla Voice

1. Download `Arduino IDE` and use the board manager/ library manager to install the default required libraries (Click Yes to install all when prompted).
2. Refer to <https://docs.arduino.cc/tutorials/nicla-voice/user-manual> to install additional firmware

## Additional Libraries for Record and Stream

1. Refer to <https://forum.arduino.cc/t/nicla-voice-record-audio/1095508> for basic background
2. Use the *Arduino IDE ⇒ File⇒ NDP ⇒ Record_and_stream* example within Arduino IDE.
3. Be sure to install the prerequisites libraries:
    - <https://github.com/pschatzmann/arduino-libg722>
    - <https://github.com/pschatzmann/arduino-audio-tools/>
4. Can place the libraries into `~\Documents/Arduino/libraries` by following this guide <https://roboticsbackend.com/install-arduino-library-from-github/>
5. For `arduino-audio-tools`, be sure to change the version to `v0.9.4` by using command `git checkout v0.9.4` as latest version has breaking changes

## Command to save recorded audio as .g722 file

After loading the program into Nicla Voice, you would need to pipe the captured audio from serial output to a file

1. Using terminal, list the used serial port via `ls /dev/tty.*`
2. Using updated `screen` program, run `screen -L -Logfile arduino_output.g722 /dev/tty.<port-number> 115200`

- example: `screen -L -Logfile arduino_output.g722 /dev/tty.usbmodem00F1F5FF3 115200`

## Open the .g722 file in Audacity

Using a program like Audacity, you can import the .g722 compressed file and play the audio
