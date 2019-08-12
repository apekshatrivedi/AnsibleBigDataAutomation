# How to Install Python and PIP on Windows 10

## Download Python
The first step is to download Python from [python.org](https://www.python.org/ "python.org") and select the most recent version to install (in this case 3.7.4).

![Download Image](https://matthewhorne.me/wp-content/uploads/2016/04/python-latest-version.png)

On the next page, scroll to the bottom of the page, you will then see a table that looks like this:

![Files Image](https://matthewhorne.me/wp-content/uploads/2016/04/download-python-installer.png)

You should select “Windows x86-64 executable installer” assuming you have a 64bit system.

## Install Python

Once it has downloaded, double-click on the installer, you will be presented with the following:

![Install Python](https://matthewhorne.me/wp-content/uploads/2016/04/python-installation-options.png)

> Note: You must ensure that you select Add Python 3.5 to PATH and then select Install Now.

If the setup ran successfully, you should see a message “Setup was successful message.” Close and continue with the next steps.

## Installing and Testing PIP

PIP is a package management system for Python, so you will want to install this handy tool to make your life simpler.

To install PIP first head over to “Get PIP,” you will see something like this:

![Pip Image](https://matthewhorne.me/wp-content/uploads/2016/04/get-pip.png)

Right-click on the link *“get-pip.py”* and select “Save Link As…”. Save it to somewhere that is easily accessible from your desktop. Once saved you will see the following on your Desktop.

![Pip Desktop](https://matthewhorne.me/wp-content/uploads/2016/04/get-pip-installer.png)

Since you have already installed Python, Windows will now understand that this is a Python script (.py) and will allow you to run it. Just double-click the file and let it run. A command prompt-like window will open and do its thing before closing again.

## Add PIP to the Windows Environment Variables

Before you can use PIP you will need to add it to the Windows Environment Variables and to do that open up `Control Panel` > `System and Security` > `System` and `select Advanced system settings` from the left-hand side, a pop-up will appear like this:

![Advance Settings](https://matthewhorne.me/wp-content/uploads/2016/04/windows-system-properties.png)

Next select Environmental Variables and under System variables locate the Path variable, then double click on it.

![Environment Variables](https://matthewhorne.me/wp-content/uploads/2016/04/windows-system-variables-path.png)

A new window will open up, select New and type the following.

`C:\Python35\Scripts`

It should look something like this.

![Paths](https://matthewhorne.me/wp-content/uploads/2016/04/add-new-enviroment-variable.png)

## How to verify if PIP is working?

To verify if PIP is working just open up command prompt and type “pip.” If it is successful you will get something like this:

![Pip powershell](https://matthewhorne.me/wp-content/uploads/2016/04/testing-pip-command-prompt.png)

Congratulations you have now installed Python and PIP on Windows 10.

## Issues
Some users have been having some issues with installing Python, I will list out some solutions as and when I come across them.

> error: The TARGETDIR variable must be provided when invoking this installer

Some windows 10 users receive this issue and the solution appears to be to run the installer with command prompt and specify the TARGETDIR (where you want to install Python).

`c:\Users\xxxx\Downloads>python-3.6.1-amd64.exe TargetDir=c:\Python36`

> Note that your path to the installer might be different and your version of python.