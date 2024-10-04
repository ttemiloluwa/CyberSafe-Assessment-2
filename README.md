# Project Summary
The project is a Flask-based API that offers a simple yet functional web application with two primary endpoints:

/: Returns a "Welcome to My Flask App!" message.
/how are you: Responds with "I am good, how about you?" when accessed.
The API is lightweight and easy to deploy, serving as a practical example of how a Python Flask app can be containerized and deployed on a Kubernetes cluster using a CI/CD pipeline.

   
## How the API was containerized
The Flask API was containerized using Docker, making it portable and isolated from the host environment. This ensures consistency across different stages of development and deployment, regardless of the underlying infrastructure.

The Dockerfile is based on ubuntu:20.04, providing a stable base for the application.
Python dependencies, including Flask, were installed in the container, and the application code (app.py) was copied into the image.
Once built, the image was stored in Docker Hub under the name ttemiloluwa/flask-app-ci-cd, from where it can be pulled for deployment.

  
   
## CI/CD Process
To automate the build, test, and deployment process, GitHub Actions was used for the CI/CD pipeline. Here’s a step-by-step breakdown of how the pipeline works:

Automated Docker Build: Every time new code is pushed to the main branch, the workflow builds the Docker image using the latest codebase.
Image Push to Docker Hub: Once the image is built, it is automatically pushed to Docker Hub under ttemiloluwa/flask-app-ci-cd.


## API deployed on Kubernetes



