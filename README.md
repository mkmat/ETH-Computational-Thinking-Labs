# ETH Computational Thinking Labs: general instructions

1. [Classroom assignments](#assignments)
2. [Reports: Markdown syntax](#markdown)
3. [Programming language: python3 interpreter](#interpreter)
4. [Run python3 from the command line](#commandline)
5. [Write python3](#language)
6. [Collaboration tool: GitHub](#github)
7. [Write and Run python3 scripts in vscode](#vscode)
8. [Collaboration tool: Live share scripts in vscode](#liveshare)
9. [Collaboration tool: Write python3 scripts in Overleaf](#overleaf)
10. [Collaboration tool: Installation-free: Run python3 in CTL-code-expert](#code-expert)
11. [Collaboration tool: Write and Run Matlab](#matlab)
12. [Where to get help](#help)


## Classroom assignments<a name="assignments"></a>
 
 You will receive an invitation for each assignment by email. Accept the assignment and choose from the existing groups, if you'd like to join any of the existing groups, or create a new group. Upon acceptance, you will find a new repository in your personal GitHub account. See [below](#github) if you don't have a GitHub account yet. 
 
### Classroom assignments in [vscode](#vscode)
 
 Start vscode. To manage your classroom assignments, click the github symbol in the left taskbar, sign in to github. To commit your changes, click the Source Control icon (Crtl-Shit-G). Always leave a message for your commits. 
 
### Classroom assignments at [GitHub](#github)

Once you accepted an assignment, you will find a new repository in your personal GitHub. You do not need to use vscode to edit your codes, you can also edit them directly at GitHub, or clone the directory to a local directory, and edit from there using another software. Make sure to commit your changes. 
 
### Classroom assignments at [Overleaf](#overleaf)

You can create a new project at Overleaf from your assignment at GitHub as described [below](#OverleafImportGitHub). Unfortunately, files ending with .py are not rendered as a text file in Overleaf, except if you create a new file.py at Overleaf and paste the content of the python script into it. Python scripts located at your Overleaf can be executed over the [CTL-code-expert online](#code-expert) tool. 
 
## Reports: Markdown syntax<a name="markdown"></a>

All information about a project other than the script itself, such as goals, ideas, results should be collected in the file report.md located at your github assignment. All group members should be enabled to edit report.md. md-files are interpreted using the Markdown syntax at GitHub. A quick reference to the Markdown syntax is available at  https://www.markdownguide.org/cheat-sheet/

## Programming language: python3 interpreter<a name="interpreter"></a>

### Install

windows, macos, linux: download from https://docs.conda.io/en/latest/miniconda.html

Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a  small number of other useful packages, including pip, zlib and a few others. Use the conda install command to install additional packages like numpy or matplotlib.

## Run python3 from the command line<a name="commandline"></a>

### Execute a python3 script from the command line

windows: search and open Command Prompt. macos and linux: Open terminal window. Switch (cd) to the directory containing your script or provide the full path of your script. Enter

    python3 [yourscript.py] [arguments]
    
Exit the interactive python3 via quit(). Display the exit value via
 
    python3 [yourscript.py] [arguments]; echo $?
    
## Write python3<a name="language"></a>

Cheat Sheets: https://cheatography.com/tag/-python/, https://www.pythoncheatsheet.org/

### Use command line arguments in your python3 script

    import sys
    ...
    # the number of command line arguments is: len(sys.argv)-1
    n = int(sys.argv[1])
    
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
 
### Exit from your python3 script with value 13

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
    
### Read and save integer-valued matrix from and to file tic-tac-toe.txt<a name=readsavematrix</a>

    import numpy as np
    data = np.genfromtxt("tic-tac-toe.txt", dtype=np.int)
    data[0,0]=1
    np.savetxt("tic-tac-toe.txt", data, fmt="%d")
    
### Create graphics file mygraphics.png<a name="graphics"></a>

    import matplotlib.pyplot as plt
    # assuming myarray (an array) carries your image
    plt.imshow(myarray)
    plt.savefig('mygraphics.png')
    
### Introduction to Python classes and related 

https://www.youtube.com/watch?v=ZDa-Z5JzLYM
    
## Collaboration tool: GitHub<a name="github"></a>

Create your personal github account at www.github.com
    
## Write and Run python3 scripts in vscode<a name="vscode"></a>
 
 Install vscode (Visual Studio Code) from https://code.visualstudio.com/download. Choose 'add to path' during installation. Start vscode, 
 1. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for python, press return. Choose python from Microsoft, install.
 2. Choose File, New File, Select File type python or enter python in the search field, press enter. Choose a file location and name. 
 3. Press Run (press the triangle) or Run+Debug or enter a python command in the TERMINAL. The output is shown in the TERMINAL and/or OUTPUT. 
 
## Collaboration tool: Live share scripts in vscode<a name="liveshare"></a>
 
 You can edit your python script simultaneously with group members or let them just read and comment on your code from within vscode + live share. If the code is located at github, all group members can open it from there (clone, fork, branch, pull ..), and commit, push, .. their modified codes. 
 
 1. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for VS live share. Choose the version from Microsoft, install.
 2. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for github pull requests and issues extension, install.
 
### Clone and use a github repository in vscode
 
 In vscode, open the command palette with Crtl-Shift-P. At the command palette prompt, enter gitcl, select the Git: Clone command, and press Enter. When prompted for the Repository URL, select clone from GitHub, then press Enter. If you are asked to sign into GitHub, complete the sign-in process. Enter the repository URL, selected or create a local directory into which you want to clone the project. 
 
### Working simultaneously on a python file in vscode
 
 In vscode, click the Live Share icon in the left taskbar. Click Share to share the file or folder you are editing. Follow the instruction and send the invitation to one or more group members, assistants, lecturer (email, skype etc). You can allow the invited person to read only or to edit your file. If you are receiving the invitation, follow the link and accept the invitation (you can join either by the vscode web interface or by your locally installed vscode). The inviting person will then let you in. You can add comments to the open files, chat etc. and change the file if you have the permission. 
 
## Collaboration tool: Write python3 scripts in Overleaf<a name="overleaf"></a>
 
 Login at https://www.overleaf.com/edu/ethz using your ETH email address. 
 
### How to: Export Overleaf project to github
 
 At Overleaf, switch to the project you want to export. Click Menu (top left), then GitHub. This will create a new repository at your github. You can choose between private and public. Pull GitHub changes to Overleaf: Menu, GitHub.  
 
### How to: Import github repository to Overleaf<a href=OverleafImportGitHub></a>
 
 At Overleaf, click the Home symbol. New Project, Import from GitHub. You will see a list of your current GitHub projects from which you can choose. 
 Push Overleaf changes to github via: Menu, GitHub. 
 
### How to: Synchronize Overleaf with your Dropbox
 
 At Overleaf, switch to the project you want to synchronize. Click Menu (top left), then Dropbox.  
 
## Collaboration tool: Installation-free: Run python3 in CTL-code-expert<a name="code-expert"></a>

To be able to edit your python scripts simultaneously with group members and to execute them without installing anything (no python, vscode, github required) you can do the following: 

1. One group member either imports the GitHub repository as a new project to his/her Overleaf (if other group members prefer to edit the code outside Overleaf) OR creates a new folder CODES, and creates a file code.py within this folder.  
2. This group member shares the project with the remaining group members (emails required, click Share in Overleaf)
3. All group members can now edit the python script at Overleaf at any time, also simultaneously. The Chat and Review features of Overleaf can be used to leave comments. 
4. To be able to execute your code.py online, you need to invite the lecturer to your project. The code can afterwards be executed at [CTL-code-expert](https://ctl.polyphys.mat.ethz.ch/cgi-bin/CTL-code-expert). The CTL-code-expert allows everybody to just execute your code (but not read or change it) and to specify parameters. It is certainly less convenient than editing and executing python via vscode, from the command line, or using another python editor. While error messages are displayed, graphics must be saved on file(s) (as described [above](#graphics)) to to get displayed. 
    
## How to: install git

Install git from https://git-scm.com/download

## Collaboration tool: Write and Run Matlab<a name=matlab></a>

Assignments can also be completed using other programming languages such as Matlab. To work with Matlab in a group consider using MATLAB Drive (it is very similat to polybox or dropbox). You need to have an account at www.mathworks.com. Login into this account through the website and search for MATLAB Drive, and install it. You can then share your files within a dedicated directory with group members. 

## Where to get help<a name=help></a>

### Help with installations and GitHub

Contact an assistant

### Help with Overleaf or CTL-code-expert

Contact the lecturer

### Help with designing your algorithm

Contact lecturer or assistant(s). 

### Help with debugging your python code

There are various options (email addresses available from the course page)
1. Send us your questions if they can be potentially answered without seeing your code. 
2. If you have vscode + live share installed, send us an invitation as described [above](#liveshare) 
3. If you are editing your code at Overleaf, invite us to your Overleaf project as described [above](#overleaf), and if done so already, write in the Overleaf chat, or contact us. 
4. Leave a message in the github classroom. 

