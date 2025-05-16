# 1. Start Minikube (if not already running)
minikube start

# 2. Enable Ingress (if not already enabled)
minikube addons enable ingress

# 3. Start Jenkins container (from Dockerfile)
cd part7
docker build -t jenkins-custom .
docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins-custom

# 4. Unlock Jenkins (get the password)
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword

# 5. Open Jenkins in browser
# (then complete setup and install suggested plugins)
http://localhost:8080

# 6. Log into Gogs (localhost:3000), create a repo, and push your code to it
# (use the Gogs web UI and Git commands)

# 7. In Jenkins, create a new pipeline job and connect it to your Gogs repo

# 8. Run the pipeline to deploy your Helm chart

# 9. Verify deployment
kubectl get pods -n widgetario
kubectl get svc -n widgetario
