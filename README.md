# Setting up zerodb for first time

##Installing on Cloud 9
- I have a workspace on Cloud 9
- and following setup instructions here https://docs.zerodb.com/

###Step 1. Get the zerodb demo files
Upload/git the files in the zerodb-server git repository https://github.com/zerodb/zerodb-server

Create a folder on the workspace on Cloud 9 in which to put the files. I called mine `zerodb_server`

###Step 2. Set up and activate the virtual environment
At the terminal type the following which creates a virtual environment folder at /.demo/:

`$ virtualenv .demo`

Then to activate the virtual environement type the following:

`$ source .demo/bin/activate`

You shoud now have `(.demo)` at the start of your terminal line showing the virtual environment is activated. 

`(.demo)username:~/workspace/zerodb_server $`

You always need to activate the virtual environment before doing anthing!

###Step 3. Install python packages required for zero-db
Navigate to the demo directory and install the necessary packages. The packages are in the file `requirements.txt`

`(.demo)username:~/workspace/zerodb_server $ pip install -r requirements.txt`

At the end of the installation you should have the following being all the packages installed:

`Successfully installed ipython click zerodb pickleshare pathlib2 setuptools traitlets pygments simplegeneric pexpect prompt-toolkit decorator backports.shutil-get-terminal-size zope.lifecycleevent jsonpickle ZEO zc.zlibstorage pycryptodome zope.component zerodbext.catalog six requests zope.index BTrees ZODB cachetools aes256gcm-nacl ecdsa scrypt flask-cors flask zodbpickle zope.event ipython-genutils ptyprocess wcwidth zope.interface transaction persistent zc.lockfile ZConfig zdaemon cffi itsdangerous Werkzeug Jinja2 pycparser MarkupSafe
Cleaning up...`

###Step 4. Initialise the database
So, to initialize a database, just run `zerodb-manage init_db`

Unfortunately, this gave me the following error indicating the terminal sripts aren't working:

`bash: zerodb-manage: command not found`

to fix this, create a file called zerodb-manage containing:

`#!/bin/bash
python zerodbext/server/db/manage.py`

Create a new directory in the root folder the following takes you to the root directory

`cd ~`

Then create a folder called bin and copy the `zerodb-manage` file into it:

`mkdir bin`

`cp zerodb-manage ~/bin`

Create two new files in the ~/bin directory called zerodb-server (which refers to the run.py file) and zerodb-api (which refers to api.py file). Now the scipts should be setup. Now we are ready to initialise the database:

`(.demo)username:~/workspace/zerodb_server $zerodb-manage init_db`

Press enter to accept root username; and type password.







