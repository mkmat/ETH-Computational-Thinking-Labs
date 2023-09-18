# ETH Computational Thinking Labs: general instructions
# This file will get updated before the begin of the semester, please ignore it for the time being.  

1. [getting started](#start)
2. [classroom assignments](#assignments)
3. [python](#python)
4. [collaboration tool: live share scripts in vscode](#liveshare)

## 1. getting started<a name="start"></a>

All relevant links for this course are collected at a single website: https://ctl.polyphys.mat.ethz.ch/, which you may bookmark. 

### get a [Github] account<a name="github">

Visit www.github.com and sign in, if you have already an account, or Sign up and create an account. You can choose your institutional email address to create an account. Check your settings like email notifactions etc. under 'Settings'.  

### installations (anaconda, VS code, git, python, classroom)<a name="install">

The following instructions reflect our recommendations on how to install a functional python environment with git integration in VS Code for working with github classroom. If you already have an environment which meets these requirements, you can ignore the instructions, but understand that we might not be able to provide assistance if you run into problems. Click on the following images if you need to enlarge them.
 
1. Check, if you have anaconda (or miniconda) installed already. If so, start the anaconda navigator and check if VS Code is one of the existing applications <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-anaconda-check-for-vscode.png" width="3%"> (or search for visual studio code/VS Code/vscode on your computer). If both are true, continue at 5. If you are missing VS Code in your anaconda navigator, close the navigator and continue at 3. Otherwise continue.
2. You have neither anaconda nor miniconda installed. Install anaconda 2.4.3 or later (not miniconda) from https://anaconda.com/download (Requires 5GB of disk space. Additional information at https://docs.anaconda.com/free/anaconda/install). Once installed successfully, start the anaconda navigator (You do not need to create an anaconda cloud account and can skip this question). Check if VS Code is an installed application <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-anaconda-check-for-vscode.png" width="3%">, if you cannot find the VS Code symbol in the list, then you need to close the anaconda navigator and continue at 3. Otherwise launch VS Code and continue at 5.
3. You need to install VS Code, hence visit http://code.visualstudio.com/download and download and install VS Code. When asked for, choose "Add to PATH", which is the default. Once installed, do not start VS Code or exit if you opened it already (On MacOS you should move the application from your download folder to your applications folder).
4. Now start the anaconda navigator again. You should have VS Code in the list of applications. Launch VS Code. Just in case you have several versions of python installed (older versions, from a previous install): you might need to manually link the python extension with the python installation from anaconda (or miniconda). The walkthrough on the VS code start screen will prompt you to select the interpreter, if you indeed have several versions installed, otherwise not. Simply choose the option containing "('base')" which is the default installation for anaconda (and miniconda).
5. Within VS Code, open a terminal from the top menu bar <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-top-menu.png" width="20%"> . Click into the terminal window, write "conda install git" <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-terminal-window.png" width="30%"> and press enter. Answer questions with yes, if there are any. 
6. Within VS Code, click on the Extensions symbol <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-symbol-extensions.png" width="2%"> in the menu bar on the left, and search for "Github Pull Requests and Issues". <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-extensions-pull-requests.png" width="30%"> Click the blue 'install' buttom (in the screenshot it is not visible as I have it already installed), and once installed, close the VS Code application.
7. Start VS Code again. This time, you should see a blue (1) at the accounts symbol <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-symbol-github.png" width="2%"> in the menu bar on the left. Click on it, and choose "Sign in with Github ..". If nothing works, be patient, check if there are more than one VS Code screen open now, and eventually choose one of the options (like local server) that are offered to sign in. Once you are signed in, the blue (1) does not appear anymore, and if you press the accounts symbol again, it should show your github name.
8. Within VS Code, click on the Extensions symbol (shown above), and search for "Github Classroom" <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-extension-classroom.png" width="30%"> Click the blue 'install' buttom. 
9. VS Code asks you again (blue 1 at the accounts symbol <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-symbol-github.png" width="2%">) for permission to connect with github. Once connected, and if there are no remaining blue numbers in the left panel, click on the github symbol <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-symbol-classroom.png" width="2%"> . Ideally, VS Code tells that you have not yet accepted any assignments. If you see this message, you are almost done. 
10. Within VS Code, click on the (well known) Extensions symbol in the menu bar on the left, and search for "Python" (from Microsoft). Click 'install'.
11. You successfully completed the whole setup and can close VS Code and anaconda. You have now installed: anaconda, python, git, VS Code, and you have a github account, and are ready to accept a classroom assignment.

If you encounter any problems during the installation process, do not hesitate to reach out to us via email or approach us in person. We can try to assist you via email or arrange a one on one meeting.

Additional steps that can be done during the CTL lecture:

1. Open a Terminal in VS code as described above. Type python --version (enter), and git --version (enter) to see if python and git are installed.
2. To finish the git configuration, execute the following commands within the Terminal, where you have to choose a XXX name (no blanks or special characters), and enter your email address:
   
     git config --global user.name "XXX"
   
     git config --global user.email XXX@YYY

4. Within VS Code. Choose File and New File from the menu bar. Select 'Python file' from the options. Enter a command like print("hello"), and then press the small triangle in the top right corner of the VS code window to save (with extension .py) and run your python file.
5. Within VS code, close Folder (if you have an open folder), then click the Github symbol <img src="http://ctl.polyphys.mat.ethz.ch/snapshots/Capture-vscode-symbol-classroom.png" width="2%">. You should see the classroom folder.


## 2. classroom assignments<a name="assignments"></a>

### accept an assignment and become member of a group
You will receive an invitation for each assignment by email. Accept the assignment and choose from the existing groups, if you'd like to join any of the existing groups, or create a new group (with a science/lecture-related name, no special characters, no blanks). Upon acceptance, you will find a new repository in your personal GitHub account. If you cannot find any place in any of the existing groups and want to create a new group, while the maximum number of groups has been reached already, please send an email. To check if it worked, login to www.github.com, click your github symbol. Check your profile. Check if you are member of the CTL organization and member of a group. If not, contact us.

### deal with classroom assignments in [vscode](#vscode)
 
Start [vscode](#vscode). To manage your classroom assignments, click the GitHub symbol in the left taskbar, sign in to GitHub. To find your classroom assignment, click on the GitHub symbol in the vscode menu bar on the left. Select and open your assignment, find your files, edit them or create a new file. To commit your changes, click the Source Control icon (Crtl-Shift-G). Always leave a message for your commits. To see the rendered markdown README.md, click on README.md (or your own md-file), and then crtl+K followed by V. To see if your committed changes in VS code have been transferred to github, visit your corresponding repository at Github, and check the time stamp of the modified file (or its content). 
 
### deal with classroom assignments at [GitHub](#github)

Once you accepted an assignment, you will find a new repository in your personal GitHub. You do not need to use vscode to edit your codes, you can also edit them directly at GitHub, or clone the directory to a local directory, and edit from there using another software. Make sure to commit your changes directly to the main branch (or create a branch + pull request, if you want your group members or assistants review your changes, and if you know what you are doing). To find back (if needed) your assignment(s) at GitHub, click https://github.com/ETH-Computational-Thinking-Lab and then on the name of the assignment.

### pull requests (avoid, if possible)
After editing a python script or markdown file, you commit your changes directly to the main branch and update the file or create a branch and pull request. If you go for a pull reuqest, leave a comment in the pull request if you have any particular question. Open pull requests are mentioned in the menu bar of your assignment. If you are assigned to review a pull request (most likely by email), or if you have the permission to review it, you can reject or merge a pull request to finally update the current script. At the 'branches' tab you can find the existing active branches, and also delete them, if they had been taken care of already. 
 
### report.md

All information about a project other than the script itself, such as goals, ideas, results should be collected in the file report.md located at your GitHub assignment. All group members should be enabled to edit report.md. md-files are interpreted using the Markdown syntax at GitHub. A quick reference to the Markdown syntax is available at  https://www.markdownguide.org/cheat-sheet/. To watch the report.md side-by-side with your code, split the window (top right), click on the report.md and press crtl+K followed by V to render the markdown file properly.  

## 3. python  <a name="python">

Cheat Sheets: https://cheatography.com/tag/-python/, https://www.pythoncheatsheet.org/

Make sure your python script have a name like script.py with proper extension py. 

vscode: If you wish to open a new file and if python is not in the list, press crtl-shift-p and search for python: interpreter, and select from this list.

### use command line arguments in your python script

    import sys
    ...
    # the number of command line arguments is: len(sys.argv)-1
    n = int(sys.argv[1])

### call a python script from the command line

If you are in vscode: Click on 'Terminal. If not, under windows: search and open Command Prompt. macos and linux: Open terminal window. Switch (cd) to the directory containing your script or provide the full path of your script. Enter

    python3 [yourscript.py] [arguments]
    
Exit the interactive python3 via quit(). Display the exit value via
 
    python3 [yourscript.py] [arguments]; echo $?
    
### General structure of Python script that can be imported or reused and also executed from the command line

    import sys

    def myfunction1 (a):
        print("first (integer) argument is "+str(a))
        
    def myfunction2 (a,b):
        print("first (integer) argument is "+str(a))
        print("2nd (float) argument is "+str(b))
    
    # do the following if called from the command line

    if len(sys.argv)-1==1:
        a = int(sys.argv[1])
        myfunction1(a)
    elif len(sys.argv)-1==2:
        a = int(sys.argv[1])
        b = float(sys.argv[2])
        myfunction2(a,b)
 
### Exit from your python3 script with exit value 13

    import sys
    ...
    sys.exit(13) 
 
### Return and exit with a value<a name=returnexit></a>

    import sys

    def myfunction (a):
        print("first (integer) argument is "+str(a))
        b = 2*a
        return b
        
    # do the following if called from the command line

    if len(sys.argv)-1==1:
        a = int(sys.argv[1])
        b = myfunction(a)
        sys.exit(int(b))
    
### Check if myfile exists from within your python script

    import os.path
    ...
    if os.path.isfile("myfile"):
      ...
    
### Read and save integer-valued matrix from and to file tic-tac-toe.txt<a name=readsavematrix></a>

    import numpy as np
    data = np.genfromtxt("tic-tac-toe.txt", dtype=np.int32)
    data[0,0]=1
    np.savetxt("tic-tac-toe.txt", data, fmt="%d")
    
### Create graphics file mygraphics.png<a name="graphics"></a>

    import matplotlib.pyplot as plt
    # assuming myarray (an array) carries your image
    plt.imshow(myarray)
    plt.savefig('mygraphics.png')
    
### python profiler<a name="profiler"></a>

Calling python with the following options 

     python3 -m cProfile -o log.profiler mypthonscript.py 
    
creates a file log.profiler that contains information about the cpu time spent in the several routines. This can be very useful to find the most time-consuming parts of your code. 

### Create mpg-movie using matplotlib

    import matplotlib.pyplot as plt
    import numpy as np
 
    # importing movie py libraries
    from moviepy.editor import VideoClip
    from moviepy.video.io.bindings import mplfig_to_npimage
 
    # numpy array
    x = np.linspace(-2, 2, 200)
 
    # duration of the video in seconds
    duration = 2
 
    # matplot subplot
    fig, ax = plt.subplots()
 
    # method to get frames
    def make_frame(t):
     
        # clear
        ax.clear()
     
        # plotting line
        ax.plot(x, np.sinc(x**2) + np.sin(x + 2 * np.pi / duration * t), lw = 3)
        ax.set_ylim(-1.5, 2.5)
     
        # returning numpy image
        return mplfig_to_npimage(fig)
 
    # creating animation
    animation = VideoClip(make_frame, duration = duration)
 
    # displaying animation with auto play and looping
    animation.ipython_display(fps = 20, loop = True, autoplay = True)
    
### python classes and related 

https://www.youtube.com/watch?v=ZDa-Z5JzLYM

### installing python (if not yet installed, or you'd like to install another version)

windows, macos, linux: download from https://docs.conda.io/en/latest/miniconda.html

Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a  small number of other useful packages, including pip, zlib and a few others. Choose install 'just for me' and 'add to path' during installation! Use the conda install command (now or later from within the vscode Terminal) to install additional packages like numpy or matplotlib.

### python environment with a specific version of python (or other modules) in vscode<a name="conda"></a>

In some cases the library you want to use does not run under the python version you installed. 
You can use older python version or older packages quite easily in vscode with the help of 
a single conda command as shown below. By default, environments are installed into the envs directory in your conda directory. 
Run conda create --help for information on specifying a different path. Below, replace
myenv by with a unique name of your new (optional) environment. Open a command prompt and execute

    conda create -n myenv python=3.7
    or 
    conda create -n myenv python=3.7 scipy=0.17.3 astroid babel
  
This will create a new directory myenv in your conda/envs directory. 
Start vscode. Press ctrl-alt-p and search for: python: select interpreter. Choose myenv from the list, if you prefer to use myenv in your current project. 
     
## 4. collaboration tool: Live share scripts in vscode<a name="liveshare"></a>
 
 You can edit your python script simultaneously with group members or let them just read and comment on your code from within vscode + live share. If the code is located at GitHub, all group members can open it from there and commit their modified codes. 
 
 1. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for VS live share. Choose the version from Microsoft, install.
  
### Working simultaneously on a python file in vscode
 
 In vscode, click the Live Share icon in the left taskbar. Click Share to share the file or folder you are editing. Follow the instruction and send the invitation to one or more group members, assistants, lecturer (email, skype etc). You can allow the invited person to read only or to edit your file. If you are receiving the invitation, follow the link and accept the invitation (you can join either by the vscode web interface or by your locally installed vscode). The inviting person will then let you in. You can add comments to the open files, chat etc. and change the file if you have the permission. 
         
## Frequently asked questions and answers are collected [here](https://github.com/ETH-Computational-Thinking-Lab/CTL-FAQ/blob/main/README.md)

