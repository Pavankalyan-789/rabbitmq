Setup Instructions
1. Create a Virtual Environment

Create and activate a Python virtual environment for the project:

python3 -m venv yash
source yash/bin/activate

2. Install Dependencies

Install all required Python packages:

pip install -r requirements.txt

3. Install and Configure RabbitMQ

Update the system and install RabbitMQ:

sudo apt update
sudo apt install rabbitmq-server -y


Enable and start the RabbitMQ server:

sudo systemctl enable rabbitmq-server
sudo systemctl start rabbitmq-server


Check the RabbitMQ status:

sudo systemctl status rabbitmq-server
sudo rabbitmqctl status


Enable the RabbitMQ management plugin:

sudo rabbitmq-plugins enable rabbitmq_management
sudo systemctl restart rabbitmq-server


Access the management interface in your browser: http://localhost:15672/

Default username: guest

Default password: guest

4. Run the Flask App

Start the Flask application:

python3 app.py

5. Install Celery

Install Celery in your virtual environment:

pip install celery

6. Run Celery Worker

In a separate terminal, activate the virtual environment again:

source myenv/bin/activate


Start the Celery worker:

celery -A app.celery worker --loglevel=info

7. Install Ngrok

Install Ngrok to expose your server publicly:

pip install pyngrok


Add your Ngrok authtoken:

ngrok authtoken 

8. Expose the Server with Ngrok

Run Ngrok to get a public URL for your Flask app:

ngrok http 5000


Ngrok will provide a public URL that can be used to access your application externally.

curl "http://localhost:5000/?sendmail=kalyanpavan7890@gmail.com"

![ 2025-10-06 at 07 32 08_acde8019](https://github.com/user-attachments/assets/e1a5865c-5706-45ad-b263-e4ab4ecf045d)
![ 2025-10-06 at 14 40 58_5c1ac840](https://github.com/user-attachments/assets/b973907b-e3e8-435d-9c31-5d9adf112ab3)

