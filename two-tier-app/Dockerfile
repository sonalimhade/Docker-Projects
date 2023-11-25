# base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# install required packages for system
RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y gcc default-libmysqlclient-dev pkg-config \
    && rm -rf /var/lib/apt/lists/*


# Copy the requirement file to container
COPY requirements.txt .

# install app dependencies
RUN pip install mysqlclient
RUN pip install --no-cache-dir -r requirements.txt


# Copy the rest of the application code
COPY . .

# Specify the command to run your app
CMD ["python","app.py"]

