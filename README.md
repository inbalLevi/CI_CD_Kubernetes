# CI_CD_Kubernetes <img src="https://i0.wp.com/beaver.co.il/wp-content/uploads/2019/10/kubernetesblog02.jpg?w=885" width="200" height="140"/>  


## Requirements:
* Install Docker on each of the virtual machines by these commands: </br>
sudo apt-get update && apt-get upgrade -y </br>
curl -fsSL https://get.docker.com/ -o get-docker.sh </br>
bash get-docker.sh </br>
sudo apt-get update && apt-get upgrade -y </br>
* Node.js 12.x or higher
* Configure an agent: [agent-pool](https://www.youtube.com/watch?v=psa8xfJ0-zI&ab_channel=Raaviblog) 
* PostgreSQL (can be installed locally using Docker)
* Free Okta developer account for account registration, login


## Steps:
* Create 2 resource groups for 2 environments- staging and production which contains: 2 AKS - Kubernetes Cluster in Microsoft’s Azure Kubernetes Service for the project infrastructure..
* Create a virtual machine and install on it docker and agent by azure devops.
* Create a container registy 
* Install the Nginx ingress controller by with the commands: 
choco install kubernetes-helm
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install my-release bitnami/nginx-ingress-controller
* Deploy the NodeWeightTracker application on AKS meeting the following requirements:
- The NodeWeightTracker application must be accessible from the internet
- The NodeWeightTracker application must be exposed to the internet on port 80
- The NodeWeightTracker must have at least 3 instances to ensure high availability
- Use configmaps/secrets to store your application configurations
- You must expose your application using the ingress controller
* Run the pipeline and check that your applications are running :)

The full process:
![image](https://user-images.githubusercontent.com/71599740/142738639-068572f2-c29b-4b4f-92d3-e6c316064c8d.png)

![image](https://user-images.githubusercontent.com/71599740/142738398-ea35b943-427f-44dc-a15a-b27efd87fbf0.png)


The staging:
![image](https://user-images.githubusercontent.com/71599740/142738408-b91dd48b-ad77-459f-97ad-0439a1a8a67c.png)

The production:
![image](https://user-images.githubusercontent.com/71599740/142738416-9c8487ad-cd14-418b-90f9-f97e9f43d551.png)



# Emphasis:
* To install all dependencies on the nodes and to deploy and run the application for the first time I've used this project - https://github.com/inbalLevi/bootcamp-app

