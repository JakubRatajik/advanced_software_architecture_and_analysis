# Starting from official base image for python
FROM python:3.13.0

# Set environment variables
# ENV VAR_NAME=var_value

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first to leverage Docker caching
## COPY package*.json ./

# Install dependencies in the container
## RUN npm install

# Optionally, if you have global dependencies, install them as well
# RUN npm install -g some_global_package

# Copy the current directory contents into the container at /usr/src/app
COPY . .

# Expose the port the app runs on
EXPOSE 8080

# The command to run your application
CMD ["python", "main.py"]
