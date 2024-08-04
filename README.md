Trying to build a VScode extension to record and store voice memos to save the hassle of writing long commit messages.
( Final Beta stage 



<!-- 
    - [Install SoX on macOS](#install-sox-on-macos)
    - [Install SoX on Windows](#install-sox-on-windows)

2. **Install SoX**:
    - SoX (Sound eXchange) is required to record audio using the `node-record-lpcm16` library. 
    - You need to install SoX on your system for the extension to work correctly.
        - You'll get an error if `SoX` is not installed.

3. **Grant Microphone Access to VSCode**:
    - You'll need to ensure that VSCode has microphone access for the extension to work correctly.
    - Read below for more details.

### Install SoX on macOS

To install SoX on macOS, use the [Homebrew](https://brew.sh/) package manager:
```sh
brew install sox
```

### Install SoX on Windows

To install SoX on Windows, download the installer for Sox on [SourceForge](https://sourceforge.net/projects/sox/) and follow the installation instructions.

### Install SoX on Linux

To install SoX on Linux, use your distribution's package manager (or Homebrew). For example, on Debian-based systems:
```sh
sudo apt-get install sox
```

## Grant Microphone Access

* You'll need to ensure that VSCode has microphone access for the extension to work.
* When you run the extension, after installing SoX, you should get prompted for VSCode microphone access.
* If you're not prompted, you might already have VSCode in your microphone permissions, in that case, you'll need to ensure its enabled:

### Grant Microphone Access on macOS

1. Open System Preferences.
2. Go to Security & Privacy.
3. Select the Privacy tab.
4. Select Microphone in the left sidebar.
5. Ensure that Visual Studio Code (or code) is listed and checked in the list of applications allowed to access the microphone.

### Grant Microphone Access on Windows

1. Open Settings.
2. Go to Privacy.
3. Select Microphone in the left sidebar.
5. Ensure that the toggle for "Allow apps to access your microphone" is turned on.
6. Scroll down and ensure that Visual Studio Code is listed and has access to the microphone.

### Grant Microphone Access on Linux

1. Open a terminal window.
2. Use the appropriate command for your Linux distribution to open the privacy settings. For example, on Ubuntu, you can use the command gnome-control-center privacy to open the privacy settings.
3. Ensure that the microphone access is granted to applications as needed.

## Usage

* After installing the extension and SoX, open a folder in VSCode.
    * If you do not open a folder, or have a set directory set, you'll receive an error stating you need to be in a project/folder/workspace.
* Use the ``>Bee Heard: New Code Memo`` command from the command palette or click the ``New Code Memo`` button in the status bar (bottom right hand corner) to start recording.
* Use the ``>Bee Heard: End Code Memo`` command from the command palette or click the ``End Code Memo`` button in the status bar (bottom right hand corner) to stop recording.
* The recorded memos will be saved in the configured directory (your current open project/directory by default):
    * A copy of the `ABOUT.md` file will be placed in the `code_memos` directory when it is created. If you use your code memos in your projects, please attach the `ABOUT.md` as a reference in the directory.
    * The `code_memos` folder will create new sub-folders with today's date each time a code memo is generated.
    * The audio files will be in [Waveform Audio File Format (wav)](https://en.wikipedia.org/wiki/WAV) format, with a naming convention of `memo_[today's date]_[sequence].wav`.
    * Each time a new memo is created for the same day, the sequence will increment by `1`.

## Commands

## Functional Commands

You can run these commands, or use the button in the status bar (bottom right hand corner) of VSCode, the choice is yours:

- **>Bee Heard: New Code Memo** (`beeHeard.newCodeMemo`): Start recording a new code memo.
- **>Bee Heard: End Code Memo** (`beeHeard.endCodeMemo`): Stop the ongoing code memo recording.

## Configuration Commands

The configuration is set so the extension works out of the box, these are optional:

- **>Bee Heard: Configure Save Path** (`beeHeard.configureSavePath`): Set a custom directory where code memos will be saved.
- **>Bee Heard: Reset Save Path** (`beeHeard.resetSavePath`): Reset the save path to the default directory. 
    - _Default: `${workspaceFolder}/code_memos`._
- **>Bee Heard: Set Max Duration** (`beeHeard.setMaxDuration`): Set the maximum duration for recordings in seconds.  
    - _Default: 300 seconds (5 minutes). Set to 0 for unlimited recording._

## Disclaimer

No data is collected with this application, it is entirely local to your machine.

## Local Install

To install the application locally run the following command to install the package dependencies:
```bash
npm install -->
