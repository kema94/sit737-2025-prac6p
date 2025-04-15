Step-by-Step Instructions 

•	Install Docker Desktop and Node.js on your machine.
•	Enable Kubernetes in Docker Desktop under Settings > Kubernetes.
•	Create a new project folder and initialize a Node.js project:
•	npm init -y
•	Install Express:
•	npm install express
•	Create an app.js file that returns:
"Hello from Docker container!" on port 3000.
•	Ensure package.json includes the default configuration and Express as a dependency.
•	Create a Dockerfile that:
o	Uses a Node.js base image
o	Sets the working directory
o	Copies app files
o	Installs dependencies
o	Exposes port 3000
o	Runs the app with node app.js

Dockerize and Push to Docker Hub
•	Build the Docker image:
•	docker build -t node-kube-app .
•	Tag the image for Docker Hub:
•	docker tag node-kube-app nishitha03/node-kube-app
•	Push the image to Docker Hub:
•	docker push nishitha03/node-kube-app



 Deploy to Kubernetes

•	Create a deployment.yaml file to deploy the app with 2 replicas using the Docker Hub image.
•	Apply the deployment:
•	kubectl apply -f deployment.yaml
•	Create a service.yaml file to expose the app using NodePort 30036.
•	Apply the service:
•	kubectl apply -f service.yaml

 Verify Deployment
 
•	Open your browser and go to:
http://localhost:30036
to confirm the app is running.
•	Check pod and service status:
•	kubectl get pods
•	kubectl get svc

