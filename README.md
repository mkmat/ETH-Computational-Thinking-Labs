# ETH Computational Thinking Labs: general instructions

1. [getting started](#start)
2. [classroom assignments](#assignments)
3. [python](#python)
4. [collaboration tool: live share scripts in vscode](#liveshare)
5. [Presentations](#presentation)
6. [Frequently asked questions](#FAQ)

## 1. getting started<a name="start"></a>  

All relevant links for this course are collected at a single website: https://ctl.polyphys.mat.ethz.ch/, which you may bookmark. The following description is a slightly extended version of the description you find at [MyCTL](https://ctl.polyphys.mat.ethz.ch/setup).  

### get a Github account<a name="github"></a>  

Visit <www.github.com> and sign in, if you have already an account, or Sign up and create an account. You can choose your institutional email address to create an account. Check your settings like email notifactions etc. under 'Settings'.  
At MyCTL, you will find information about the projects and your groups, as well as further instructions. Please visit this site after setting up your github account.

### installations (anaconda, VS code, git, python)<a name="install"></a>  

The following instructions reflect our recommendations on how to install a functional python environment with git integration in VS Code for working with github. We outline two installation options, one being more manual, but also lighter, while the other installs a larger coding environment, including a number of apps that we do not use. If you already have an environment which meets these requirements, you can ignore the instructions, but understand that we might not be able to provide optimal assistance if you run into problems. Click on the following images if you need to enlarge them.

Important Notes:

1. On Windows machines, please make sure to select the "Add Miniconda3 to my PATH environment variable" or "Add Anaconda3 to my PATH environment variable" setting during the installation process, and not the other options. This will ensure, that other programmes can find the correct python environment.
2. If you have an intel Mac or would like to simply avoid the registration on the anaconda website, you can find the full list of build packages in the following repositories: [miniconda](https://repo.anaconda.com/miniconda/), and [anaconda](https://repo.anaconda.com/archive/).

#### Option 1: Miniconda

We recommend installing python and optionally miniconda, especially if you prefer a smaller, more hands-on coding environment. To install miniconda, please follow the instructions on the [anaconda website](https://www.anaconda.com/docs/getting-started/miniconda/system-requirements). *For anaconda installation, please see below.*

- Windows: [<https://www.anaconda.com/docs/getting-started/miniconda/install/windows-gui-install>]
- Mac: [<https://www.anaconda.com/docs/getting-started/miniconda/install/mac-gui-install>]

#### Option 2: Anaconda

If you want a hands-off, complete installation, choose anaconda. *Miniconda instructions above.*

To install anaconda, please follow the instructions on the official [anaconda website](https://www.anaconda.com/docs/getting-started/anaconda/system-requirements).  

- Windows: [<https://www.anaconda.com/docs/getting-started/anaconda/install/windows-gui-install>]
- Mac: [<https://www.anaconda.com/docs/getting-started/anaconda/install/mac-gui-install>]

Please verify that VS Code is included in your anaconda navigator by launching it after the installation has concluded. While anaconda includes VS Code, we nonetheless recommend a separate installation.

#### git

To share files remotely and collaborate on code, we use git through github. On Windows, we recommend downloading it from the [official website](https://git-scm.com/install/). On Mac, the best option is through Xcode Command Line Tools through terminal or you will be prompted automatically the first time you try to use it. For manual installation, open the App Terminal or open VS Code then select Terminal>New Terminal. Here type "xcode-select --install" and follow the instructions on screen. This will often take a few minutes to complete.

- Windows: [<https://git-scm.com/install/windows>]
- Mac: [<https://developer.apple.com/documentation/xcode/installing-the-command-line-tools>]

#### VS Code

After installing miniconda, please download the latest version of Visual Studio Code
(VS Code) from the [official download page](https://code.visualstudio.com/Download) and install.

#### Verifying installation

Once complete, open VS Code and select "open…", then select or create a folder to use for testing.
Next, select "New file…", then select "Python File". This will create a temporary python file.

After opening a python file in VS Code, please check the python version in the bottom right corner of the editor. There you should find a number similar to "3.xx.xx (base)". 
Next, try running a simple "print('Hello World!')". To run code, you can select the play button in the top right corner of your VS Code window, which will prompt you to save the file if you have not done so already. However, remember to save the file every time you insert new code, otherwise VS Code will run the last save.

Next, to verify git, use the terminal created after running the test file or create a new one by selecting Terminal>New Terminal in VS Code. Type "git -v" followed by "enter" to see your git version. If this is successful, you can complete your local git installation by entering the following three lines of commands into your terminal one after another. Replace the text in " with your account information from github.

    git config --global user.name "XXX"
    git config --global user.email "XXX@YYY"
    git config --global pull.rebase false

We will guide you through the connection with your github account during the first lecture, and we will update this description afterwards. We will also introduce you to core features of the conda environment.

#### Important Comments

In case you encounter any issues during this part of the installation process, do not worry. This is somewhat expected, so we will provide further instructions and offer our assistance during the first lecture. You can also reach out to us via email or approach us in person at any time.

If you would like some additional guidance during the installation process, we recommend the following two videos for installing anaconda (https://www.youtube.com/watch?v=xfAcErzOKN4) and VS Code (https://www.youtube.com/watch?v=HvAjnpA6mlA). The creator, Luke Barousse, uses many similar tools and a very similar installation process.

## 2. classroom assignments<a name="assignments"></a>

All instructions concerning classroom assignmnets are available at <a href="https://ctl.polyphys.mat.ethz.ch/setup">MyCTL</a>
 
### report.md<a name="report"></a>

All information about a project other than the script itself, such as goals, ideas, problems, results should be collected in the file report.md located at your GitHub assignment. All group members should be enabled to edit report.md. md-files are interpreted using the Markdown syntax at GitHub. A quick reference to the Markdown syntax is available at  https://www.markdownguide.org/cheat-sheet/. To watch the report.md side-by-side with your code, split the window (top right), click on the report.md and press crtl+K followed by V to render the markdown file properly.  To add an image to the report.md file, first upload the image file (say, myfile.png) to your repository. Then edit the report.md file and add

    <img src="myfile.png" width=50%>

## 3. python  <a name="python"></a>

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

    from sys import argv

    def myfunction1 (a):
        print("first (integer) argument is "+str(a))
        
    def myfunction2 (a,b):
        print("first (integer) argument is "+str(a))
        print("2nd (float) argument is "+str(b))
    
    # do the following if called from the command line

    if len(argv)-1==1:
        a = int(argv[1])
        myfunction1(a)
    elif len(argv)-1==2:
        a = int(argv[1])
        b = float(argv[2])
        myfunction2(a,b)
 
### Exit from your python3 script with exit value 13

    import sys
    ...
    sys.exit(13) 
 
### Return and exit with a value<a name=returnexit></a>

    import sys
    from sys import argv

    def myfunction (a):
        print("first (integer) argument is "+str(a))
        b = 2*a
        return b
        
    # do the following if called from the command line

    if len(argv)-1==1:
        a = int(argv[1])
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

## 5. Presentations<a name="presentation"></a>

Towards the end of the semester, each group presents its work during a 8 minutes talk. During these 8 minutes, group members should equally contribute to the presentation. The presentation should include the following:  

1. how did the group work together (communication channel)
2. how did we approach the problems stated by the assignments (ideas)
3. did we encounter problems, and eventually solved them, and how?
4. how have individual functions been tested (example)?
5. how did we test the code?
6. Selected results obtained with the codes
7. If you like: Criticism, suggestions for improvements

DO NOT: 

1. repeat the task descriptions
2. show your code (only a few lines, if meaningful)

Collect all your slides on one of your laptops, and save the presentation also on a stick (or at one of your github repositories).  
         
## 6. Frequently asked questions and answers are collected [here](https://github.com/ETH-Computational-Thinking-Lab/CTL-FAQ/blob/main/README.md) <a name="FAQ">


