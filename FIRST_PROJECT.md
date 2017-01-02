# Configuring a learning environment
The [introduction](README.md) provides concrete examples of how, in 20 lines of code or less, you can use Python to get better work done faster.

Now, you might be thinking, "But that code looks like gibberish. Will I actually be to do this stuff myself?" The answer is an emphatic YES! And the best way to demonstrate this is for you to set up a local learning environment where you can start writing your own code and seeing it working and failing, and troubleshooting why it failed.

### System Requirements
This configuration is geared toward individuals with their own computer running OSX 10.5 or higher. This does not provide instruction on how to implement this setup on Windows.

### Downloading Anaconda
Python 2 comes natively installed on OSX, but I recommend learning on Python 3, as it is under active development and increasingly supported by the community. Sometimes, research groups will bundle multiple Python libraries together into a consolidated *distribution* of the language. I recommend downloading the Anaconda distribution of Python 3, maintained by Continuum Analytics and [available here](https://www.continuum.io/downloads#osx). If you are new to programming, select the "Graphical Installer" option.

### Downloading Homebrew
Homebrew is a utility for installing certain types of applications onto your Mac. We are downloading Homebrew here so that we can download autoenv in the next step. To install Homebrew, open the Terminal application on your computer and copy and paste this code into the window:

    $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

If you are asked for your system password, be aware that it *will not appear as you type it into Terminal*. This is by design, but it can be confusing at first. Just type in your password and press Enter.

If you've never used Terminal before, I know it can feel scary at first. But in one sense it's just a more advanced version of Finder, which you probably use all the time on your Mac. You primarily use it to navigate between folder directories, open and move files, and download programs from the internet without opening a web browser. I highly recommend Codecademy's [Learn the Command Line](https://www.codecademy.com/en/courses/learn-the-command-line/lessons/navigation/exercises/your-first-command) course, which rapidly demystifies the whole thing.

### Downloading autoenv
Once you've installed Homebrew, it's time to install autoenv. Without getting too much into the weeds here, segregating your project environments into separate "virtual" environments is a critically important best practice which you might as well learn at the outset of your journey. The environment specifies the name and dependencies of that particular project, including the version of Python you are using (e.g., 2.x vs 3.x), the external libraries you want to download, and the specific versions of those libraries you want to reference. **When you don't segregate your project environments, you run into a lot of annoying errors system down the road**, so let's try to avoid that now.

autoenv is a utility that automatically starts a virtual environment whenever you navigate into a project directory with an active .env file. To install, paste the following two lines into Terminal.

    $ brew install autoenv
    $ echo "source $(brew --prefix autoenv)/activate.sh" >> ~/.bash_profile

### Downloading Atom
You're probably already familiar with text editors like Microsoft Word or TextEdit. For writing code, it's best to use a specialized programming text editor. Sublime Text is popular, but I recommend using Atom, available from Github [here](https://atom.io/).

### Creating your first project
Now you are ready to create your first project! Create a new folder on your Desktop called Projects. You can either do this the old fashioned way (through Finder), but I recommend learning how to do it in the command line by opening a new Terminal window and inputting the following command:

    $ cd Desktop
    $ mkdir Projects
Within the Projects folder, create a sub-folder called first_project.


Open Atom and save a file called environment.yml within first_project. Within Atom, write:

    name: first_project
    dependencies:
      - python=3.5
      - numpy
      - pandas
      - jupyter
      - pip:
        - requests

Now let's instantiate this environment. First make sure you are in the project directory. Open a new Terminal window and type:

    cd Desktop/Projects/first_project
 Your prompt should now read:

    <your computer's name>:first_project <your user name>$

At this point you are ready to create a virtual environment within this directory. Enter the following command into Terminal:

    conda env create

Terminal will now download only those dependencies specified in the environment.yml file.

Within Atom, create another file in the same directory called ".env" and write a single line of text into the file.  

    source activate first_project

Now, whenever you navigate to this project directory (i.e., by using the cd command in Terminal), autoenv will launch .env file, prompting Terminal to launch a virtual environment containing all of your required libraries for this project and nothing else.

Should you ever decide you want to reference one of the thousands of other Python libraries available (indeed, this is one of the great strengths of Python), simply add it to the environment.yml file and type

    conda env update

### Opening your first Jupyter notebook
You may have noticed that the examples stored in this repository's code_samples file utilize a file extension .ipynb. You are probably used to seeing file extensions like .txt (for text files) or .pdf, but not .ipynb. It stands for an IPython notebook file. An IPython notebook is a tool for interactive Python development that is more editable and user-friendly than a Terminal shell and provides more feedback than executing a .py file. IPython has rebranded itself as Jupyter.

To launch a Jupyter notebook, navigate to your project directory and type:

    jupyter notebook

A new browser window should open, with a graphical representation of your project directory. Beneath the hood, your computer has launched a private local server capable of interpreting and executing Python code. On the right hand side, click New, then select Python [conda env: first_project]. You now have your first notebook!

Built-in libraries, as well as the dependencies you defined in your environment.yml file, can be incorporated into your notebook by using the import statement, e.g.,

    import pandas as pd

### Time to freestyle
 Try to replicate the examples in the code_samples folder. For the spreadsheet_transformation notebook to work, you  will need to download the sample dataset, available [here](https://github.com/ptiger10/better-work-done-faster/blob/master/resources/sample_data.csv). Take liberties and see where things break.

If you want to experiment with other operations, you can find how Pandas implements many common Excel functions [here](http://davefort.org/shortcut_directory.html). I also highly recommend [Chris Albon's blog](http://chrisalbon.com/), which illustrates how to execute many tasks in Python and Pandas.

If you encounter an error, go to Google and try searching for the operation you are trying to execute, e.g., "how do I create a new column in Pandas." Odds are you are not the first person to have had this question, and others in the open source community will often have volunteered an answer with a demonstration of exactly what to do.

### Conclusion

That's all, folks. Hopefully, going through this process has affirmed that 1) learning Python will help you get better work done faster, and 2) writing useful Python yourself is not some fantastical pipe dream, but something you can start *today*.

With any luck it has also given you a clearer sense of your learning destination. Unless you have a tolerance for pain and deep reservoir of intrinsic motivation, your goal right now should *not* be to master the language. That would take 10,000 hours and is a recipe for a flamed-out new year's resolution! Your goal should be to become proficient in using the language to help you get better work done faster, and then to layer on enough understanding of fundamentals to resolve errors that pop up along the way. The Python community, especially answers on [StackOverflow](www.stackoverflow.com), are an invaluable resource on this front.

As you get more advanced and ambitious, you will want to graduate from mimicry and hackery to real understanding. At that point, it will become more appropriate to dive into the weeds of the language so that you can avoid unnecessary errors and approach a problem strategically. Here again I recommend the myriad online Python tutorials.

But after enough experimentation on your end, you might find that you don't *need* a tutorial, because you will have built up intuition about what works and what doesn't work; what is required in some situations but not others; the common conventions behind the language, etc. This intuition will empower you to reference the [core Python documentation](https://docs.python.org/3/) and library documentation (e.g., [Pandas](http://pandas.pydata.org/pandas-docs/stable/)) for yourself, which are the source from which all tutorials spring. They tend to be extremely detailed but utterly impenetrable to novices. Once you are at that point, you will start to reach escape learning velocity.

Happy trails!
