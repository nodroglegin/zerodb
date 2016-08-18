We are going to use Flask Blueprints to create a user module

###Step 1 Create a new folder called user and a file therein called views.py
The user views.py file will initially create a Blueprint called user_app and apply it to /login view function:

`from flask import Blueprint

user_app = Blueprint('user_app', __name__)

@user_app.rout('/login')
def login():
    return "user login"`


###Step 2. Update the application.py file to reference the new blueprint

`
from flask import Flask

def create_app():
    app = Flask(__name__)
    app.config.from_pyfile('settings.py')
    
    from user.views import user_app
    app.register_blueprint(user_app)
    
    return app
`
