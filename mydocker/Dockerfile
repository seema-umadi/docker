FROM ubuntu:latest
workdir /app
copy . /app
run apt-get update && apt-get install -y python3 python3-pip
cmd ["python3", "app.py"]
