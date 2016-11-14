# Adding Sublime to Your PATH

The command wasn’t found because Sublime Text isn’t in your PATH. The things in your Windows PATH are accessible via the command line so we’ll need to go ahead and add it. We will need to go into our Environment Variables settings. Do this by going to:

System Properties -> Advanced System Settings -> Advanced -> Environment Variables

A nice shortcut to do this is to open up your command line and typing sysdm.cpl. That will open up the window we need.

Create a New System Variable Create a new system variable called SUBLIME that will point to the folder of your Sublime installation.



Add the System Variable to Your PATH Add the following to the end of your PATH variable: ;%SUBLIME%


# subl.exe Into New Sublime Window

You now have the ability to open a file or folder in a new Sublime window. Just find the one you want and type:

subl.exe file_name or subl.exe folder_name


# subl.exe Into Same Sublime Window

To open files or folders into the current Sublime Text window, just add the --add modifier to your subl.exe command.

subl.exe file_name --add or subl.exe folder_name --add


##### Source [Scotch.io]("https://scotch.io/tutorials/open-sublime-text-from-the-command-line-using-subl-exe-windows")