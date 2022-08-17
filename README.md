# ETH Computational Thinking Labs: general instructions

0. [Relevant links](#links)
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

## 0. Relevant links<a name="links"></a>

All relevant links for this course are collected at a single website: https://ctl.polyphys.mat.ethz.ch/, which you may bookmark. 

## 1. Classroom assignments<a name="assignments"></a>

### accept an assignment and become member of a group
 You will receive an invitation for each assignment by email. Accept the assignment and choose from the existing groups, if you'd like to join any of the existing groups, or create a new group. Upon acceptance, you will find a new repository in your personal GitHub account. See [below](#github) if you don't have a GitHub account yet.  
 
### Classroom assignments at [GitHub](#github)

Once you accepted an assignment, you will find a new repository in your personal GitHub. You do not need to use vscode to edit your codes, you can also edit them directly at GitHub, or clone the directory to a local directory, and edit from there using another software. Make sure to commit your changes. 

To always find back your assignment(s) at GitHub, click https://github.com/ETH-Computational-Thinking-Lab and then on the name of the assignment.

### communicate with group members
To communicate with your group members about issues related to this particular assignment, you may use 'Issues' tab having entered your assignment at GitHub

<img src=./images/capture-issues.png>

### start a discussion
To communicate with the lecturer+assistants (go up one level in github, and click Teams, i.e.) 
switch to https://github.com/orgs/ETH-Computational-Thinking-Lab/teams, and then click your group. 

<img src=./images/capture-teams.png>

Here you can reply to existing questions, or start a new discussion.

### publish your modified files
After editing a python script or markdown file, you commit your changes directly and update the file, or create a branch + pull request, if you want your group members or assistants review your changes. These are the only two options you have when submitting your changed file. Leave a comment in the pull request if you have any particular question. Open pull requests are mentioned in the menu bar of your assignment. If you are assigned to review a pull request (most likely by email), or if you have the permission to review it, you can reject or merge a pull request to finally update the current script. At the 'branches' tab you can find the existing active branches, and also delete them, if they had been taken care of already. 
 
### Classroom assignments in [vscode](#vscode)
 
 Start [vscode](#vscode). To manage your classroom assignments, click the GitHub symbol in the left taskbar, sign in to GitHub. To commit your changes, click the Source Control icon (Crtl-Shit-G). Always leave a message for your commits.  
 
### Classroom assignments at [Overleaf](#overleaf)

You can create a new project at [Overleaf](#overleaf) from your assignment at GitHub as described [below](#OverleafImportGitHub). Unfortunately, files ending with .py are not rendered as a text file in Overleaf, except if you create a new file.py at Overleaf and paste the content of the python script into it. Python scripts located at your Overleaf can be executed over the [CTL-code-expert online](#code-expert) tool. 
 
## 2. Reports: Markdown syntax<a name="markdown"></a>

All information about a project other than the script itself, such as goals, ideas, results should be collected in the file report.md located at your GitHub assignment. All group members should be enabled to edit report.md. md-files are interpreted using the Markdown syntax at GitHub. A quick reference to the Markdown syntax is available at  https://www.markdownguide.org/cheat-sheet/

## 3. Programming language: python3 interpreter<a name="interpreter"></a>

### Install

windows, macos, linux: download from https://docs.conda.io/en/latest/miniconda.html

Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a  small number of other useful packages, including pip, zlib and a few others. Use the conda install command to install additional packages like numpy or matplotlib.

### Create environment with a specific version of python (or other modules) in vscode<a name="conda"></a>

In some cases the library you want to use does not run under the python version you installed. 
You can use older python version or older packages quite easily in vscode with the help of 
a single conda command as shown below. By default, environments are installed into the envs directory in your conda directory. 
Run conda create --help for information on specifying a different path. Below, replace
myenv by with a unique name of your new (optional) environment. Open a command prompt and execute

    conda create -n myenv python=3.7
    or 
    conda create -n myenv python=3.7 scipy=0.17.3 astroid babel
  
This will create a new directory myenv in your conda/envs directory. 
Start vscpde. Press ctrl-alt-p and search for: python: select interpreter. Choose myenv from the list, if you prefer to use myenv in your current project. 

## 4. Run python3 from the command line<a name="commandline"></a>

### Execute a python3 script from the command line

windows: search and open Command Prompt. macos and linux: Open terminal window. Switch (cd) to the directory containing your script or provide the full path of your script. Enter

    python3 [yourscript.py] [arguments]
    
Exit the interactive python3 via quit(). Display the exit value via
 
    python3 [yourscript.py] [arguments]; echo $?
    
## 5. Write python3<a name="language"></a>

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
    
### Read and save integer-valued matrix from and to file tic-tac-toe.txt<a name=readsavematrix></a>

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
    
## 6. Collaboration tool: GitHub<a name="github"></a>

Create your personal GitHub account at www.github.com

Check your settings like email notifactions etc. under 'Settings'. 
    
## 7. Write and Run python3 scripts in vscode<a name="vscode"></a>
 
 Install vscode (Visual Studio Code) from https://code.visualstudio.com/download. Choose 'add to path' during installation. Start vscode, 
 1. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for python, press return. Choose python from Microsoft, install.
 2. Choose File, New File, Select File type python (if it exists) or choose text file (and afterwards follow: Select a Language, select python. If python is not in the list, press crtl-shift-p and search for python: interpreter, and select from the list). Choose a file location and name. 
 3. Press Run (press the triangle) or Run+Debug or enter a python command in the TERMINAL. The output is shown in the TERMINAL and/or OUTPUT. 
 
## 8. Collaboration tool: Live share scripts in vscode<a name="liveshare"></a>
 
 You can edit your python script simultaneously with group members or let them just read and comment on your code from within vscode + live share. If the code is located at GitHub, all group members can open it from there (clone, fork, branch, pull ..), and commit, push, .. their modified codes. 
 
 1. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for VS live share. Choose the version from Microsoft, install.
 2. click on the Extensions symbol in the left taskbar (Crtl-shift-X). Search for GitHub pull requests and issues extension, install.
 
### Clone and use a GitHub repository in vscode
 
 In vscode, open the command palette with Crtl-Shift-P. At the command palette prompt, enter gitcl, select the Git: Clone command, and press Enter. When prompted for the Repository URL, select clone from GitHub, then press Enter. If you are asked to sign into GitHub, complete the sign-in process. Enter the repository URL, selected or create a local directory into which you want to clone the project. 
 
### Working simultaneously on a python file in vscode
 
 In vscode, click the Live Share icon in the left taskbar. Click Share to share the file or folder you are editing. Follow the instruction and send the invitation to one or more group members, assistants, lecturer (email, skype etc). You can allow the invited person to read only or to edit your file. If you are receiving the invitation, follow the link and accept the invitation (you can join either by the vscode web interface or by your locally installed vscode). The inviting person will then let you in. You can add comments to the open files, chat etc. and change the file if you have the permission. 
 
## 9. Collaboration tool: Write python3 scripts in Overleaf<a name="overleaf"></a>
 
 Login at https://www.overleaf.com/edu/ethz using your ETH email address. 
 
### How to: Export Overleaf project to GitHub
 
 At Overleaf, switch to the project you want to export. Click Menu (top left), then GitHub. This will create a new repository at your GitHub. You can choose between private and public. Pull GitHub changes to Overleaf: Menu, GitHub.  
 
### How to: Import github repository to Overleaf<a href=OverleafImportGitHub></a>
 
 At Overleaf, click the Home symbol. New Project, Import from GitHub. You will see a list of your current GitHub projects from which you can choose. 
 Push Overleaf changes to github via: Menu, GitHub. 
 
### How to: Synchronize Overleaf with your Dropbox
 
 At Overleaf, switch to the project you want to synchronize. Click Menu (top left), then Dropbox.  
 
## 10. Collaboration tool: Installation-free: Run python3 in CTL-code-expert<a name="code-expert"></a>

To be able to edit your python scripts simultaneously with group members and to execute them without installing anything (no python, vscode, GitHub required) you can do the following: 

1. One group member either imports the GitHub repository as a new project to his/her Overleaf (if other group members prefer to edit the code outside Overleaf) OR creates a new folder CODES, and creates a file code.py within this folder.  
2. This group member shares the project with the remaining group members (emails required, click Share in Overleaf)
3. All group members can now edit the python script at Overleaf at any time, also simultaneously. The Chat and Review features of Overleaf can be used to leave comments. 
4. To be able to execute your code.py online, you need to invite the lecturer to your project. The code can afterwards be executed at [CTL-code-expert](https://ctl.polyphys.mat.ethz.ch/cgi-bin/CTL-code-expert). The CTL-code-expert allows everybody to just execute your code (but not read or change it) and to specify parameters. It is certainly less convenient than editing and executing python via vscode, from the command line, or using another python editor. While error messages are displayed, graphics must be saved on file(s) (as described [above](#graphics)) to to get displayed. 
    
## How to: install git

Install git from https://git-scm.com/download

## 11. Collaboration tool: Write and Run Matlab<a name=matlab></a>

Assignments can also be completed using other programming languages such as Matlab. To work with Matlab in a group consider using MATLAB Drive (it is very similat to polybox or dropbox). You need to have an account at www.mathworks.com. Login into this account through the website and search for MATLAB Drive, and install it. You can then share your files within a dedicated directory with group members. 

## 12. Where to get help<a name=help></a>

### Help with installations and GitHub

Contact an assistant

### Help with Overleaf or CTL-code-expert

Contact the lecturer

### Help with designing your algorithm

Contact lecturer or assistant(s). 

### Help with debugging your python code

There are various options (email addresses available from the course page)
1. Leave a message in the Discussion section of your group at [ETH-Computational-Thinking-Lab/teams](https://github.com/orgs/ETH-Computational-Thinking-Lab/teams). 
2. If you have vscode + live share installed, send us an invitation as described [above](#liveshare) or arrange a date with any of us by email or through 'Discussion' 
4. If you are editing your code at Overleaf, invite us to your Overleaf project as described [above](#overleaf), and if done so already, write in the Overleaf chat, or contact us. 


