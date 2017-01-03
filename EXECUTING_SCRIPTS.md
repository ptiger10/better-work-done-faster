# Executing Python scripts
In the previous [section](FIRST_PROJECT.md), you learned how to set up a local environment for rapid learning. Jupyter notebooks are excellent for learning, rapid iteration, and troubleshooting, but are not the most efficient means of executing commands and implementing Python logic. For that, you should convert your notebooks into scripts and run the scripts directly in the Terminal.

To convert a Jupyter notebook into a Python script, follow these steps:
- In the last line of the notebook, type out the following code snippet, but do not run the code:

      #!jupyter nbconvert --to=python {Notebook_Name}.ipynb

- Save your notebook (Command + S)
- Delete the # at the front of the code snippet and execute the code.
- Following these steps ensures that the nbconvert command will execute but will not be included in the script itself.
- NB: For this to work, the notebook name cannot have any spaces.

If the process was successful, you should now have a new file in your directory entitled {Notebook_Name}.py. To run this script, just enter the following instruction into Terminal:

    python {Notebook_Name}.py

The Terminal shell will output any consequences of the code, such as printing any print(x) statements or creating new files. For example, if you include this code at the end of spreadsheet_transformation.py, it will download the revised spreadsheet to your directory as a .csv file:

    df.to_csv('revised_data.csv')

### Conclusion
That's all, folks. Hopefully, going through this process has affirmed that 1) learning Python will help you get better work done faster, and 2) writing useful Python yourself is not some fantastical pipe dream, but something you can start *today*.

With any luck it has also given you a clearer sense of your learning destination. Unless you have a high tolerance for pain and deep reservoir of intrinsic motivation, your goal right now should *not* be to master the language. That would take 10,000 hours and is a recipe for a flamed-out new year's resolution! Your goal should be to become proficient enough in using the language to start getting better work done faster, and then to layer on enough understanding of fundamentals to resolve errors that pop up along the way. The Python community, especially answers on [StackOverflow](www.stackoverflow.com), are an invaluable resource on this front.

As you get more advanced and ambitious, you will want to graduate from mimicry and hackery to real understanding. At that point, it will become more appropriate to dive into the weeds of the language so that you can avoid unnecessary errors and approach problems more strategically. Here again I recommend the myriad online Python tutorials.

But after enough experimentation on your end, you might find that you don't *need* a tutorial, because you will have built up intuition about what works and what doesn't work; what is required in some situations but not others; the common conventions behind the language, etc. This intuition will empower you to reference the [core Python documentation](https://docs.python.org/3/) and library documentation (e.g., [Pandas](http://pandas.pydata.org/pandas-docs/stable/)) directly, which are the source from which all tutorials spring. They tend to be extremely rich and detailed but utterly impenetrable to novices. Once you are at that point, your learning trajectory will start to reach escape velocity.

Happy trails!
