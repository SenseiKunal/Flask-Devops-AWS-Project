# DevOps Flask Project

Simple Flask application containerized with Docker and deployable on AWS EC2.

## Run locally (without Docker)
```bash
pip install -r requirements.txt
python app.py
```
Open http://localhost:5000

## Run with Docker
```bash
docker build -t flask-devops-app .
docker run -p 5000:5000 flask-devops-app
```

## Deploy on AWS EC2 (Amazon Linux)
```bash
sudo yum update -y
sudo yum install docker -y
sudo service docker start
sudo usermod -aG docker ec2-user
# logout and login again

git clone <your-repo>
cd devops-flask-project
docker build -t flask-devops-app .
docker run -d -p 80:5000 flask-devops-app
```
Then open http://<your-ec2-public-ip>
