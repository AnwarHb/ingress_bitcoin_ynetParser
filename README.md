# Ingress Bitcoin App and Ynet Parser

This is a follow-up task of the bitcoin application (show the bitcoin price and average) and the ynet parser application (XML to HTML parser), 
The aim is to create an ingress API object that manages external access to the two services while they are running in a Kubernetes cluster.

#### Projects : 
- you can find the bitcoin application here:
 [https://github.com/AnwarHb/bitcoinApp](https://github.com/AnwarHb/bitcoinApp)
- you can find the ynet parser application here:
 [https://github.com/AnwarHb/ynet_parser](https://github.com/AnwarHb/ynet_parser)
 
####  Images : 
for every application  a docker image was created and pushed to Docker Hub :
- to pull the bitcoin image: `docker pull anwarhb/docker_bitcoin:latest`
- to pull the ynet_parser image: `docker pull anwarhb/ynet_parser:latest`

#### Run Code in minikube:
- Clone the code: 
`git clone https://github.com/AnwarHb/ingress_bitcoin_ynetParser.git`

- Start minikube and enable the ingress addon if needed:
`minikube start`
`minikube addons enable ingress`

- Apply the yaml files to create the pods and services needed:

` kubectl apply -f bitcoin_deployment.yml`

`kubectl apply -f ynet_deployment.yml`

` kubectl apply -f ingress_deploy.yml`
  or  ` kubectl apply -f .`
- To be able to access ports running in a tunnel is needed (in windows):
`minikube tunnel`


- you can access the bitcoin application with
[http://localhost/bitcoin](http://localhost/bitcoin)
[![](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/bitcoin.png?raw=true)](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/bitcoin.png?raw=true)

- you can access the ynet parser application with [http://localhost/ynet_parser](http://localhost/ynet_parser)
[![](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/ynet_parser.png?raw=true)](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/ynet_parser.png?raw=true)

#### services and pods :
- pods : 
[![](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/pods.png?raw=true)](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/pods.png?raw=true)
- services :
[![](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/services.png?raw=true)](https://github.com/AnwarHb/ingress_bitcoin_ynetParser/blob/main/services.png?raw=true)
