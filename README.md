## This is a simple app using Python Flask
### How to **Deploy** an app using _python flask_ on _Ubuntu_ :

1. Prepare Your App
* Create Python file  
 Example:  
```python
from flask import Flask
# Create the Flask app
app = Flask(__name__)
# Define a simple route
@app.route('/')
def hello_world():
    return 'Hello, World!'
# Run the app
if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
# Create the Flask app
app = Flask(__name__)
# Define a simple route
@app.route('/')
def home():
    return "Welcome to the Flask App!"
```

2. Choose a Hosting Platform (Example AWS)

- Launch a virtual server (instance) 

    - Choose an AMI and Instance type
    - Create a key pair
    - Launch instance   
  
3. Connect to virtual server
   
* Navigate to the Directory with the your-key.pem File 
* Open the Terminal
* Connect to your instance using its Public DNS:  
```
ssh -i username@instance-public-ip your-key.pem
```

4. Clone repository from GitHub (Optional)
* Go to the repository's main page on GitHub
* Click the Code and Copy URL to clipboard
* Open terminal and clone your repository content :  
```
git clone https://github.com/username/repository.git
```

5. Install Python and Flask

```
* sudo apt update 
* sudo apt install python3 python3-pip 
* sudo apt install python3-venv
* sudo apt install python3-flask
```

6. Run app

 * Locate Python app file
 
  ```
 FLASK_APP=app.py flask run --host=0.0.0.0 --port=5000 
```
7. Add a security group 

* Go to Instances -> Security -> Security groups 
* Edit inbound rule
* Add rule:
    * Type: Custom TCP
    * Protocol: TPC
    * Port range: 5000
    * Source type: Anywhere-IPv4
    * Source: 0.0.0.0/0
* Save rules
