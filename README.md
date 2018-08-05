# Meeting Decline ![logo](Room17DE.MeetingDecline/Resources/MeetingDeclineImage.png "Logo")

### About
Outlook addin for automatically declining meeting requests received in certain folders.

### Features
- decline a meeting received in a folder
- or say tentative to it
- and send optional response with an optional message

### Install
TBA

### Usage
- Right click on any folder and select `Meeting Decline`

  ![main](screenshots/main.png?raw=true "main")

  _Note: If you have many folders in your inbox, it will take a bit until the list is populated._

- Hover your mouse over the folder name to see it's full path:

  ![hover](screenshots/hover.png?raw=true "hover")

- Check `Enabled` box to start declining email:

  ![enable](screenshots/enable.png?raw=true "enable")

- Choose what action needs to be taken when receiving the meeting, between `Decline` or `Tentative`:

  ![choose](screenshots/choose.png?raw=true "choose")

- Optional, check `Send response` to send a response to the Meeting organizer, if he wanted to:

  ![response](screenshots/response.png?raw=true "response")

- Optional, click on `Message` link to add a custom message for response message:

    ![message](screenshots/message.png?raw=true "message")

    - A new window will appear where you can type in your message:

    ![input](screenshots/input.png?raw=true "input")

    - Click `OK` to save it, or `Cancel` to revert changes.

- That's it! Click `OK` to save everything or `Cancel` to discard changes. The application will start listening to new emails and decline them according to your rules.
  ![finish](screenshots/finish.png?raw=true "finish")
  
### Submit an issue
TBA
  
### Development
Software Required:
- Visual Studio (minimum 2015, recomended 2017)
- Visual Studio Tools for Office (VSTO) - see in Visual Studio Installer
- .NET Framework >=4.5.2
- Microsoft Outlook

Initial build required a _non_ existent `.pfx` and `.snk` file in project directory to sign the assembly. Go to Project `Properties` -> `Signing`:
- select any option between `Select from Store...`, `Select from File...` or `Create Test Certificate...` to add another `.pfx` file
- untick `Sign the assembly` or generate a new `.snk` file under `Choose a strong name key file` -> `<New...>`

While debugging, Visual Studio will install the addin, start a new instance of Outlook.exe and attach the debugger to it. You may find usefull to set the environment variable `VSTO_SUPPRESSDISPLAYALERTS` to `0` so Outlook will report any uncaught exception from addin via a popup.

Use these steps in case Outlook doesn't want to load the addin:
- go to `File` -> `Options` -> `Add-ins`
  - if the addin is listed `Inactive Application Add-ins`
    - select `COM Add-ins` under `Manage:` (lower page section) then click `Go...`
    - check addin name and click OK
  - if the addin is listed under `Disabled Application Add-ins`
    - select `Disabled Items` under `Manage:` (lower page section) then click `Go...`
    - select the addin and click Enable
- restart Outlook
        
    
