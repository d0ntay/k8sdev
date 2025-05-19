# Here is a k8s deployment I did on my home lab.
I am running esxi on my dell r420. I spun up 3 nodes. 1 Control Plane node(rke2-server) and 2 Worker nodes(rke2-agent). I am using RKE2 as my kubernetes distribution.
First I built a golang app that is just a simple api that allows me to run a quick curl command to verify my app is up and running. I then containerized my application
and pushed it to docker hub. I then setup up my cluster and installed helm whioh I then used to install argocd as my gitops solution. From here I was able to create my 
own helm chart which deploys my custom golang app. I then pushed that helm chart to github (this repo) and then linked this github to argocd for deployment. From here my
application has been deployed and I able to make changes to my helm chart and push them, allowing argocd to automatically spin up new pods with the updated changes made
in my helm chart.
