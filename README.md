# Discord Voice Chat Text to Speech Bot
This Discord bot allows users to talk in a voice chat without the use of a microphone. With the use of a Text to Speech service such as IBM Watson, it's possible to convert a Discord user's text messages to speech.

-----------
## **Installation**
These steps will get you up and running as soon as possible.

**General installation**:

Follow these steps to install the bot regardless of your platform.

1. Clone this repository.
2. Install the Python dependencies by running the `pip install -r requirements.txt` command in a terminal window. This will install all of the needed Python libraries that are listed in the `requirements.txt` file.
3. Edit the following variables in the `main.py` file:
    - `bot_prefix`: Changing this is optional, but you can change your Discord bot's prefix if you want
    - `DISCORD_TOKEN`: Your Discord bot's token 
        - Can be found on your [Discord developer portal](https://discord.com/developers/applications)
    - `IBM_WATSON_API_KEY`: Your IBM Watson Text to Speech service API key 
        - Can be found on your [IBM Cloud dashboard](https://cloud.ibm.com/)
    - `IBM_WATSON_URL`: Your IBM Watson Text to Speech service API URL 
        - Can be found on your [IBM Cloud dashboard](https://cloud.ibm.com/)
    - `IBM_WATSON_DEFAULT_ACCENT`: Changing this is optional, but you can change your Discord bot's default accent
4. If you'd like to limit the bot's usage to certain individuals or restrict its access to specific text channels, you can edit the `user_ids` and `channel_ids` variables accordingly.

**Windows-specific**:

If you're on Windows, follow these additional steps in order to get the bot's voice chat module to run:

1. Edit the `version` variable in the `main.py` file by changing its value to "W" for "Windows".
2. Go to the following [link](https://github.com/BtbN/FFmpeg-Builds/releases/download/latest/ffmpeg-master-latest-win64-gpl.zip) to install a Windows version of the FFmpeg software (please note that clicking on the link above will automatically start the download process). This software is needed in order to get the bot to talk in voice channels.
3. Extract the zip file anywhere on your PC and copy the "ffmpeg.exe" file which can be found in the "bin" directory of the zip file you've just extracted.
4. Paste the "ffmpeg.exe" file in the "bin" directory of the Discord bot folder.
5. To start the bot, you can either:
    - Run the following command in a terminal window: `python main.py`
    
        or

    - Double click the `run.bat` file, which runs the `python main.py` command on its own. Please note that you'll have to edit the bat file accordingly if you change the script's name.

**Linux-specific**:

If you're on Linux (most likely because you'd like to host the bot on a server), follow these additional steps in order to get the bot's voice chat module to run:

1. Edit the `version` variable in the `main.py` file by changing its value to "L" for "Linux".
2. In a terminal window, run the following command: `sudo apt install ffmpeg`
3. To start the bot, you can run the following command in a terminal window: `python main.py`

-----------
## **Usage**
Now that you've successfully completed the installation process, you're ready to start using the bot! Assuming you've already invited it to one of your servers and you've got enough permissions to use it, you can run a couple of commands to get started.

**If you're already in a voice channel:**
1. Type `.join` (or "`PREFIX`join" if you've decided to change the bot's prefix) in any text channel - this will tell the bot to join the voice channel you're currently in.
2. The bot should now dictate the messages being sent in any valid text channel.
3. Type `.leave` (or "`PREFIX`leave" if you've decided to change the bot's prefix) if you want the bot to leave the voice channel it's currently in. This will also reset it and delete all of the MP3 files that it used during the session.

**If you're not  in a voice channel:**
1. Type `.join CHANNEL_ID` (or "`PREFIX`join CHANNEL_ID" if you've decided to change the bot's prefix) in any text channel - this will tell the bot to join the voice channel you're specified in the command.
2. The bot should now dictate the messages being sent in any valid text channel without you being in the voice channel.
3. Type `.leave` (or "`PREFIX`leave" if you've decided to change the bot's prefix) if you want the bot to leave the voice channel it's currently in. This will also reset it by deleting all of the MP3 files that it used during the session and change its accent to the default one.

**Additional commands:**
- You can get a list of accents by running the `.accents` (or "`PREFIX`accents") command. This will return a list of accents as shown in the following screenshot:
![List of accents command](https://i.gyazo.com/b3000f07d09ef56528db80798e2a782a.png)
- You can change the bot's accent by running the `.accent ACCENT` (or "`PREFIX`accent ACCENT") command, as shown in the screenshot below. Please note that the command must be taken from the list of accents generated from the `.accents` (or "`PREFIX`accents") command.
![Changing the bot's accent](https://i.gyazo.com/49cb89e5fecf5c328a468456a159a1b9.png)