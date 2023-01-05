# RBTray
## Introduction
This is a fork from [Nikolay Redko](http://rbtray.sourceforge.net/) work.  
The original application hides the window and adds its icon to the system tray. My version has two differences:
- The icon is constantly updated.
- The window is not hidden.

## How to use
Start `RBTray.exe` (you might want to make it start with windows) and right click the minimize button of the window you want its icon to be shown in the system tray. You can do this for a max of 64 windows.  
You can right click the icon to quit the application (which will remove every icon from the tray), close the window or remove only its icon from the tray.  
You can also left click the icon to send the window to the foreground (and change the current desktop to the one which contains it, if you are on Windows 10).

## Development
Any issues or pull requests are welcome and I'll try to make time to answer them. 

### Updating the icon
Currently, every icon is updated each time the application gets a message. This is bad for two reasons:
- It's an expensive operation.
- It may not reflect the changes very quickly.

I believe the right way of doing this would be subscribing to an event which is triggered when the window status (icon, title) is changed, but I'm afrad I don't have the proper Windows API or C++ knowledge to achieve this.

### Exiting
Currently, exiting the application is not killing its proccess.

## Alternatives
The only alternative I found for this behavior is called [Actual Window Manager](https://www.actualtools.com/windowmanager/), but it's not free, although it has a 60 days trial. I tested it and it works perfectly. It also has some very other useful features, the tray icon is just a small feature.
