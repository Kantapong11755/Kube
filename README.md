
# Kube project     
#### My divice     
 OS : windowns 11      
 CPU : 6 core     
 RAM : 8 Gb          
 Storege : 512 Gb       
#### Tools     
 Kubectl     
 Minikube     
 Docker for Desktop       
 Wsl2 ( linux Ubantu )
 

### Wakatime Kube
 - [https://wakatime.com/@spcn12/projects/ivfefhesbh]    
      
### Kubectl
 - [https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/]    
     
### Minikube
 - [https://minikube.sigs.k8s.io/docs/start/]    
### Install Docker desktop  
 - [https://www.docker.com/products/docker-desktop/]      
 
### Traefik deploy on docker
 [https://github.com/iamapinan/kubeplay-traefik]
     
![image](https://user-images.githubusercontent.com/116998478/225642506-e6951c99-48c1-4bd3-95c4-8ce572f41ef3.png)    
        
        
## >> Enable virtual mode in Bios <<
         
### 1.Install kubectl
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
      
![image](https://user-images.githubusercontent.com/116998478/225642936-074fd6aa-1fcb-4daa-b586-499445097ba4.png)       


### 2.Install mini kube windows
 - Run this command in powershell(admin) to install minikube
```
 New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing
```
 - Check path after install     
        
 ![minikube](https://user-images.githubusercontent.com/116998478/225668225-725ca1dc-d9cc-4e3c-b2cb-5b726dc6f0e9.png)

 ### 3.Install Docker for Desktop
 ### 4.Install wsl2 linux for windows (Docker require)
  - Run this command for install Wsl2
```
wsl --install
```     
    
-----------------------------------------------------------------------------------------------------------------------------

### Traefik deploy on minikube  
#### 1.Install Traefik Resource Definitions and RBAC for Traefik 
```
kubectl apply -f https://raw.githubusercontent.com/traefik/traefik/v2.9/docs/content/reference/dynamic-configuration/kubernetes-crd-definition-v1.yml
kubectl apply -f https://raw.githubusercontent.com/traefik/traefik/v2.9/docs/content/reference/dynamic-configuration/kubernetes-crd-rbac.yml
``` 

### 2.Install Traefik Helmchart
```
helm repo add traefik https://traefik.github.io/charts
helm repo update
helm install traefik traefik/traefik
```
### 3.Run this code to create secrete
```
htpasswd -nB user | tee auth-secret
kubectl create secret generic -n traefik dashboard-auth-secret --from-   file=users=auth-secret -o yaml --dry-run=client | tee dashboard-secret.yaml
```
### 4.Change namespace in traefik-dashboard.yaml file.
### 5.Run this command to view ip host.
```
kubectl get svc
```
### 6.Add ip host in host file this path C:\Windows\System32\drivers\etc
### 7.Go to host to check result.
```
https://traefik.spcn12.local
```    

![image](https://user-images.githubusercontent.com/116998478/226189710-2a0924ba-ed9a-4eae-a682-cd029600a2df.png)

```
http://web.spcn12.local
```     
![image](https://user-images.githubusercontent.com/116998478/226189908-c3d52aea-154d-4b8f-8e74-09d14539fe9d.png)











 
