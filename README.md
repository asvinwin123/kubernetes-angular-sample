# kubernetes-angular-sample
Explain you about how to host a angular application in minikube kubernetes cluster

# Pre requisites
```
Minikube setup is already done.
If minikube is not installed kindly follow,
https://gist.github.com/gonzaloplaza/f62fdcfdb6aac3d15a0fe0d750715729
```

# Start minikube
```
minikube start
```

# Open minikube dashboard
```
minikube dashboard
```

# Clone the repository
```
https://github.com/asvinwin123/kubernetes-angular-sample.git
```

# Run docker
```
cd kubernetes-angular-sample
cd angular-app

Build a docker image using below command, instead of asvinwin123 provide your github username,
docker build --rm -t asvinwin123/angular-app .

Check the docker image is created using,
docker images
```

# Push docker image to docker hub
```
Login to docker using docker credentials,
docker login

Push docker file use your username instead of asvinwin123,
docker push asvinwin123/angular-app

Check the image is pushed to docker hub repository in the browser. 
```

# Run deployment
```
Go to root folder,
cd kubernetes-angular-sample

Open and update deployment file in terminal,
vim deployment.yaml

Change the image name instead of asvinwin123 give your username.
asvinwin123/angular-app -> yourusername/angular-app

Run the deployment yaml file,
kubectl create -f deployment.yaml
```

go to minikube dashboard and check the deployment and pods tab. verify the pods are in running state.

# Verify in cmd line
```
kubectl get pods
kubectl get deployments
kubectl get services
```

# Open the angular application
```
get the minikube ip using
minikube ip
in browser open to see the hello wrold app running in port 30001, 
http://minikubeip:30001
```

# Remove the application from minikube
```
kubectl delete -f deployment.yaml
```

