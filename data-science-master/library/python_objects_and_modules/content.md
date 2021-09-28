---
title: Objects and modules
author: Thinkful
team: grading
time: 120 minutes
uuid: 186cc634-f4ac-4ead-8502-90eb3357e4c2
timeHours: 2
---

## Working with modules
Knowing what modules are and working with them can be two different things altogether. So, in this checkpoint, you'll explore how to work with modules. 

First, check to see if the module that you want is installed:

```python
pip list | grep <module_name_you_want_to_check>
```


**Note:** These commands must be run in a terminal or command-line window. To run them from within Jupyter Notebooks, place an exclamation mark `!` in front of the command.

If you installed Python using Anaconda, many of the common packages that you will want to use, such as NumPy, will already be installed. You can get the entire list of modules that are installed in your current Python environment using `pip list`. Or, if you're working in Jupyter, use `!pip list` instead.

### Installing modules
There are three main ways that you can install a package. The one that you choose will depend on your current Python management setup and preference.

Imagine that you want to install the GeoPandas module for working with spatial data in Python. Here are your three options:

- If you use the Conda package manager, use `conda install geopandas`.
- If you prefer pip, use `pip install geopandas`.
- And if you'd like to install directly from the source, use `pip install git+git://github.com/geopandas/geopandas.git`.

If you're installing a module directly from Jupyter Notebook using pip, start a new cell and type `!pip install geopandas`.

### Loading modules
Once you have the packages that you need installed, you need to load them by running import commands. For example, to load pandas, type `import pandas as pd`. Then, any time that you want to call a function from the pandas module, indicate that by prefacing it with `pd.`. Module import statements should be at the beginning of your program or Jupyter Notebook, with one statement per line. That will look similar to this:

```python
import numpy as np
import pandas as pd
import scipy
from datetime import datetime
```

Import statements that include `from` statements are *absolute imports*. That means that they load only the specified function from the module, rather than all of the functions in that module. When you only need one or two functions from a module, absolute imports are recommended because they result in more understandable error messages and cleaner code.

### Dependencies
Some packages will have *dependencies*, which are other modules that they depend on to run properly. You can check the dependencies of a package using the `pip show module_name` command. When installing a package, you may encounter a missing dependent module for the package that you're trying to install. Simply install the dependent modules first, and then proceed with installing the module you would like to use. The package documentation will most likely list the core dependent and optional dependent packages. To see an example, visit the [GeoPandas page](https://geopandas.org/install.html).

If you encounter a module loading error, it is likely that a dependent package is missing. Or, if you're running code from someone else, you might be missing an entire module. If you can't discern what the error is indicating, search for the message on [Stack Overflow](https://stackoverflow.com/questions/tagged/python). Most likely, someone else will have posted the same error, and you'll be able to find community responses to help. 

## Objects
It's time to talk about something you've been using every time you write Python, but that you may not have been thinking about: *objects*. You've been using objects all along, because *everything* in Python is an object. 

Integers? Objects.

Strings? Objects. 

Lists, dictionaries, booleans, and even functions—all of these are objects.

Objects and object-oriented programming are deep topics that cut to the core of Python and computer science. But in practice, as a data scientist, you don't need to explore this topic deeply. Mainly, you'll need to be able to recognize objects when you see them, and you'll need to know how to interact with objects in your code. Practice in the Notebook below.

<jupyter notebook-name="working_with_objects_modules_libraries" course-code="DSBC"></jupyter>

Check out the two videos below for screencast demonstrations of the topics covered in this checkpoint.

<iframe id="kaltura_player_1590583233" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590583233&entry_id=1_hcekna31" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


<iframe id="kaltura_player_1590583258" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590583258&entry_id=1_jpr3iiro" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>
