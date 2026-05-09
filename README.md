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
- Get your chat ID (send a message to your bot, then check @UserInfo3Bot)

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

## Security Notes

- This tool is for educational purposes only
- Unauthorized keylogging is illegal and unethical
- Use only on devices you own or have explicit permission to monitor

## Disclaimer

The author is not responsible for any misuse of this software.