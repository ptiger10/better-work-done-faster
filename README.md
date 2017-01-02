# better-work-done-faster
A repository to help people learn Python so they can get better work done faster.

Python is a general purpose programming language. The purpose of these materials is to help you learn Python and apply it to improve your life.

The materials are organized around a learning philosophy that suits me, but may not be right for you. The philosophy is:

- Engage your intrinsic motivation by showing how Python can help you get better work done faster.
- Guide you in setting up an environment where you can test things rapidly and see the results for yourself.
- Dive into the fundamentals of the language only as necessary to achieve specific goals.

This philosophy stands in contrast to many tutorials about Python, which start with grounding the student in fundamental concepts and methodologies. While that is probably the best approach for learning a new language comprehensively, it requires a lot of time and patience, and many mid-career learners will lose interest before they ever see how Python can actually help them!

These materials reference Python 3.x. If you are trying to learn Python 2.x, I would recommend [Google's Python Class](https://developers.google.com/edu/python/).

## What can I do with Python at work?
### Spreadsheets
If your work involves performing tasks in spreadsheets, then Python can help you get better work done faster.

Imagine you are overseeing a Swedish orchard harvest. Every day you download a .csv file or Excel spreadsheet detailing the day's haul. Unfortunately, the file is never formatted in the right way, and you need to modify it before you can do your analysis. How annoying!

Imagine that your file looks like this:

![Start Table](resources/table1.png)

And you need to make these modifications:
- A "European Pear" should be called a "Continental Fruit" and a "Red Apple" should be called a "Pomme Rouge."
- The Amt Picked and Sale Value should be quoted in kilograms and €/kilogram, not lbs and $/lb respectively.
- An additional column should calculate the total € earned by each person for each day's harvest.
- An additional column should tally the cumulative € that each harvester has earned that day.
- A final column should calculate the collective time spent harvesting each item's Product Category on that day, across all harvesters.

If you have ever worked with a spreadsheet, odds are that you have spent countless hours making changes just like these, over and over again. These mindless tasks sap your creative energy, distract you from more impactful analysis, and are difficult to troubleshoot if you encounter errors. Worst of all, when you download this file tomorrow, you have to make the same rote changes all over again.

With Python, you can write a script that executes all these tasks for you in seconds! And the best part is, once you've written the script once, you can run it as many times as you want and it will always run the same way. Like they say in the old Ronco infomercials, you just ["Set It and Forget It!"](https://www.youtube.com/watch?v=tLq27iOW0R0)

With just 20 lines of code, available [here](spreadsheet_transformation.ipynb), we can transform the spreadsheet to suit our purposes.

Et voila! The spreadsheet is now ready for whatever needs to happen next, from sending it along as a report to running a more advanced analysis.
![End Table](resources/table2.png)

### Web Data
If your work involves gathering data from the web, then Python can help you get better work done faster.

Imagine you are an astronomer in Houston trying to check whether any human space activities are interfering with your celestial readings. Every day, you visit the [NASA website](https://www.nasa.gov/) to read the latest events, like the ones below:
![NASA Table](resources/nasa_table.png)

One day, you realize that you don't actually care about seeing all of NASA's events, because reading through this list every day is burning valuable time. All you want is to be alerted whenever something is happening at the Johnson Space Center.

With Python, you can write a script to read through text on the web *for you* and extract interesting bits.


### Conclusion

These examples are just the tip of the iceberg for demonstrating the power and utility of Python at work. Since the purpose of these materials is to empower you to do these things and more on your own, it's almost time to dive into some of the fundamentals at play here. But first, let's configure your environment.
