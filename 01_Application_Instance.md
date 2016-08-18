# we are first going to create an application instance of Flask following basic factory structure

###Step 1. Create application.py file
In directory that contains demo.py create a new file called `application.py` containing the following:

`from flask import Flask

def create_app():
    app = Flask(__name__)
    app.config.from_pyfile('settings.py')
    return app
`

###Step 2. Create settings.py file
In the same directory create a new file called settings.py which to begin with will only contain:

`DEBUG=True`

###Step 3. Create manage.py file
In the same directory create a new file called manage.py which contains the folllowing code:

`import os, sys
sys.path.append(os.path.abspath(os.path.join(os.path.dirname(__file__), '..')))

from flask.ext.script import Manager, Server
from application import create_app

app = create_app()
manager=Manager(app)

manager.add_command("runserver", Server(
    use_debugger=True,
    use_reloader=True, 
    host=os.getenv('IP', '0.0.0.0'),
    port=int(os.getenv('PORT', 5000)))
    )

if __name__ == "__main__":
    manager.run()
`

###Step 4. Test that set up has worked
At command line type:

`$ python manage.py runserver`
