
      
# Kube project with Debian11
### Wakatime Kube
 - [https://wakatime.com/@spcn12/projects/ivfefhesbh]    
      
### Kubectl Debian
 - [https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/]    
     
### Minikube
 - [https://minikube.sigs.k8s.io/docs/start/]    
### Install Docker desktop  
 - [https://www.docker.com/products/docker-desktop/]    
     
![image](https://user-images.githubusercontent.com/116998478/225642506-e6951c99-48c1-4bd3-95c4-8ce572f41ef3.png)    
         
         
### Install kubectl
 - Run this command in cmd to install kubectl
```
curl.exe -LO "https://dl.k8s.io/release/v1.26.0/bin/windows/amd64/kubectl.exe"    
curl.exe -LO "https://dl.k8s.io/v1.26.0/bin/windows/amd64/kubectl.exe.sha256"
```
 - Go to edit environment variables and new path for kubectl    
      
![Screenshot 2023-03-16 205139](https://user-images.githubusercontent.com/116998478/225638655-b0735ff7-1f5f-442d-b9fe-a8ad5410f03e.png)    
```
C:\kubetcl
```
 - Run this command to check install
```
 kubectl version --client --output=yaml
```
    
        
![image](https://user-images.githubusercontent.com/116998478/225634675-2fe94ad1-30f7-439f-85e9-dd266dc4fd16.png)    
      
![image](https://user-images.githubusercontent.com/116998478/225642506-e6951c99-48c1-4bd3-95c4-8ce572f41ef3.png)       


### Install mini kube windows
 - Run this command in powershell(admin) to install minikube
```
 New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing
```
 - Check path after install     
        
 ![minikube](https://user-images.githubusercontent.com/116998478/225668225-725ca1dc-d9cc-4e3c-b2cb-5b726dc6f0e9.png)

 
