# How to Install Python and PIP on Windows 10

## Download Python

The first step is to download Python from [python.org](https://www.python.org/ "python.org") and select the most recent version to install (in this case 3.7.4).

[![Downloads.png](https://i.postimg.cc/QMFS4JGj/Downloads.png)](https://postimg.cc/SXpWj8xP "Downloads.png")

On the next page, scroll to the bottom of the page, you will then see a table that looks like this:

[![files.png](https://i.postimg.cc/vm1Frn0V/files.png)](https://postimg.cc/HJChHrDY "files.png")

You should select `Windows x86-64 executable installer` assuming you have a 64bit system.

## Install Python

Once it has downloaded, double-click on the installer, you will be presented with the following:

[![Installpython.png](https://i.postimg.cc/V61gfQ0k/Installpython.png)](https://postimg.cc/8FKM4Yb2 "Installpython.png")

> Note: You must ensure that you select Add Python 3.5 to PATH and then select Install Now.

If the setup ran successfully, you should see a message **“Setup was successful message.”** Close and continue with the next steps.

[![pythonsetupsuccess.png](https://i.postimg.cc/KYYLJGTL/pythonsetupsuccess.png)](https://postimg.cc/87qjCVtP "pythonsetupsuccess.png")

## Installing and Testing PIP

PIP is a package management system for Python, so you will want to install this handy tool to make your life simpler.

To install PIP first head over to “ [Get PIP](https://bootstrap.pypa.io/get-pip.py "Get PIP")”

Right click on the code and Save the script to somewhere that is easily accessible from your desktop. Once saved you will see the following on your Desktop.

[![get-pip.png](https://i.postimg.cc/Yqby99tL/get-pip.png)](https://postimg.cc/Czn4rwBw "get-pip.png")

Since you have already installed Python, Windows will now understand that this is a Python script (.py) and will allow you to run it. Just double-click the file and let it run. A command prompt-like window will open and do its thing before closing again.

[![installingpip.png](https://i.postimg.cc/B6p2gjYx/installingpip.png)](https://postimg.cc/HcJJWkCx "installingpip.png")

## Add PIP to the Windows Environment Variables

Before you can use PIP you will need to add it to the Windows Environment Variables and to do that open up `Control Panel` > `System and Security` > `System` and `select Advanced system settings` from the left-hand side, a pop-up will appear like this:

[![advancesettings.png](https://i.postimg.cc/c40wzByf/advancesettings.png)](https://postimg.cc/QVYF95MM "advancesettings.png")

Next select Environmental Variables and under System variables locate the Path variable, then double click on it.

[![environmentvariables.png](https://i.postimg.cc/Y9tt70pD/environmentvariables.png)](https://postimg.cc/3yfsCK02 "environmentvariables.png")

A new window will open up, select New and type the following.

`C:\Python35\Scripts`

It should look something like this.

[![paths.png](https://i.postimg.cc/Jhq9bqLK/paths.png)](https://postimg.cc/XZrHW9Xy "paths.png") 

## How to verify if PIP is working?

To verify if PIP is working just open up command prompt and type “pip.” If it is successful you will get something like this:

[![powershell.png](https://i.postimg.cc/qv0rygKJ/powershell.png)](https://postimg.cc/PP60kXK9 "powershell.png")

Congratulations you have now installed Python and PIP on Windows 10.

## Issues
Some users have been having some issues with installing Python, I will list out some solutions as and when I come across them.

> error: The TARGETDIR variable must be provided when invoking this installer

Some windows 10 users receive this issue and the solution appears to be to run the installer with command prompt and specify the TARGETDIR (where you want to install Python).

`c:\Users\xxxx\Downloads>python-3.6.1-amd64.exe TargetDir=c:\Python36`

> Note that your path to the installer might be different and your version of python.

## References

1. Images screenshots markdownlinks obtain from: [https://postimage.org](https://postimage.org "https://postimage.org")
2. Tutorial: [https://matthewhorne.me/how-to-install-python-and-pip-on-windows-10/](https://matthewhorne.me/how-to-install-python-and-pip-on-windows-10/ "matthewhorne.me")