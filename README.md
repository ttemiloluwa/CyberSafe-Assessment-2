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

Build the Docker Image: The pipeline automatically builds the Docker image for the Flask API, ensuring that the latest changes are included.
Push to Docker Hub: Once the image is built, it is pushed to Docker Hub,under ttemiloluwa/flask-app-ci-cd. making it available for deployment.

Deployment on Kubernetes: After pushing the image, the pipeline triggers the deployment process, which updates the application on our Kubernetes cluster.



## API deployed on Kubernetes
The API is deployed on a Kubernetes cluster, inorder to leverage its orchestration capabilities for scaling, load balancing, and managing the application lifecycle. I defined deployment and service configurations in YAML files that specify how many replicas of the application should run and how they should be exposed to external traffic. This setup ensures high availability and resilience, as Kubernetes automatically manages the application’s state.


## Security Measures Implemented

Several measures to safeguard the API and its environment were implemented:

Docker Image Security: Ubuntu:20.04,  a minimal base image ensures that dependencies are regularly updated to minimize vulnerabilities.

Environment Isolation: The API runs in a containerized environment, isolating it from the host system and reducing the risk of system-wide attacks.

Kubernetes Best Practices: Kubernetes features such as replicas for redundancy and NodePort services for controlled access was utilized.

Secure Credentials Management: All sensitive information, such as Docker Hub credentials, is stored in GitHub Secrets, preventing exposure in the codebase.


