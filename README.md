notebooks
=========
IPython Notebooks by Scott Sanderson

Running IPython Notebook
------------------------
Assuming you have the below dependencies installed, you can run a local
notebook server by running:
```
ipython notebook --matplotlib=inline --notebook-dir=path/to/directory/containing/notebooks
```
If you're already in the directory containing your notebook, you can omit the `--notebook-dir` flag.


Once your server is running, you can open, run, and edit your notebooks by going to your browser and
entering `127.0.0.1:8888` as the URL. `127.0.0.1` tells your browser to connect to your computer rather
than to a remote server, and `:8888` tells it to connect to port 8888, which is the default port on which
`ipython notebook` runs.  You can change the port for the server by passing `--port=<number>`.

Creating an Isolated Python Environment
---------------------------------------
I highly recommend using [`virtualenv`](https://pypi.python.org/pypi/virtualenv)
for maintaining isolated python installs for particular projects.  I also use
the excellent [`virtualenvwrapper`](http://virtualenvwrapper.readthedocs.org/en/latest/)
library, which provides a nicer interface for displaying and switching between
virtualenvs.  You can get both of these modules by running:
```
pip install virtualenv virtualenvwrapper
```
Assuming you have both `virtualenv` and `virtualenvwrapper` installed, you can
create an isolated environment for these notebooks by running
```
mkvirtualenv <env_name>
```
(where you can replace <env_name> with the name you actually want to use).

You can then switch between environments using the `workon` command
##### Example
```
workon notebook_env
\# Do notebook stuff.
...
workon some_other_project_env
\# Do other_project stuff.
```

Installing Dependencies
-----------------------

1. If you haven't already done so, create a virtual environment so we 
   have a clean slate and don't interfere with any other projects.
2. Install `IPython` with all optional dependencies by running
   `pip install ipython[all]`
3. Install `zipline` by running `pip install zipline`.  This will also install `zipline`'s 
   dependencies, including
   - `numpy`
   - `scipy`
   - `pandas`
4. Install `matplotlib` by running `pip install matplotlib`.  If this is your first time installing 
   `matplotlib`, you may get errors complaining that you're missing certain C libraries.  If you're on
   `OSX` I recommend [Homebrew](http://brew.sh/) for installing these dependencies.  It provides an
   interface similar to package managers like `apt-get` or `yum` that you might use on a Linux
   distribution.
