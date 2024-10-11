# TODO-BE
This is a TODO computer application, it is a CS50 Final Project.
#### Video Demo: [Here](https://www.youtube.com/)

---

#### Description:
##### Brief introduction:
This app is simply a todo list little manager that is powered entirely by python.
It uses the tkinter library which is a famous python library for making GUI Apps.
The tkinter library is slightly out-dated, it is easy to set off but a bit challenging to implement "modern" style in apps.
Feel free to look at the app code, possibly making a PR? It's totally up to you!
##### About the app:
First you may notice this app contains 3 files:
- app.py
- requirements.txt
- .gitignore
<br>
app.py is the main file for the app, .gitignore is the file which contains the files I want to ignore when commiting changes to git. The requirements file contains all the packages that must be installed to run this app. Let's talk about app.py (the main file).

##### app.py
This is a python tkinter app. It uses tkinter's grid system as well as relative positioning system.
It uses 2 constants for storing colors for this app. It uses colors from bootstrap, a popular web framework.
As you go into the main function, first you notice is_first_time, which basically checks if there are no tasks stored in the "database" (which are stored in a json file). A SQL database could've been used, but I used json in this case for convience.

The app will automatically create a folder for tasks named "tasks", in which a json file will be stored, which will contain all your tasks. so the first couple of lines make sure that the tasks folder and the json file are created.
Then, there is a function to set grid weight automatically in a window. and also you find a function which handles errors in user input (providing no task name or too long task name, no priority, etc ..).

Then the create task function, which basically creates a new task and then stores it in the json file, each task could optionally have a discription so it also stores it there. If no discription provided, discription will be set simply to `""` in the json file.

Also about the refresh tasks function, it's whole purpose is to delete all the task widgets in a particular window, in order to display updated tasks, with added, deleted, or new tasks.

You could choose from three priorities: High, middle, or low. These are stores in the json file (Note that they must be provided).

Then tkinter style is configured for each of different widgets like labels and entries. This is the best practice to stylize widgets in ttk (themed tkinter), but it doesn't work so well with some widgets like buttons, hence sometimes style is applied directly to widget with tk instead of applying it indirectly with ttk.

