# Setting up zerodb for first time

##Installing on Cloud 9
- I have a workspace on Cloud 9
- and following setup instructions here https://docs.zerodb.com/

###Step 1. Get the zerodb demo files
Upload/git the files in the zerodb-server git repository https://github.com/zerodb/zerodb-server

Create a folder on the workspace on Cloud 9 in which to put the files. I called mine `zerodb_server`

###Step 2. Set up and activate the virtual environment
At the terminal type the following which creates a virtual environement folder at /.demo/:

`$ virtualenv .demo`

Then to activate the virtual environement:

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





