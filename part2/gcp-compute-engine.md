1- Install SDK

echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
 2020  sudo apt-get install apt-transport-https ca-certificates gnupg
 2021  curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -
 2022  sudo apt update && sudo apt install google-cloud-sdk
 2023  sudo apt install google-cloud-sdk


2- Login in
gcloud init

3- Select project

Pick cloud project to use: 
 [1] bq-taw-data  
 [2] cloud-solutions-group  
 [3] cloudshell-images  
 [4] dw-workshop  
 [5] hcls-testing-data  
 [6] qwiklabs-gcp-04-c26ac218452c  
 [7] qwiklabs-resources  
 [8] Create a new project  
 Please enter numeric choice or text value (must exactly match list 
item):  6

4- Define Zone
gcloud config set compute/zone us-central1-a

5- Create a vm

gcloud compute instances create "my-vm-3" --machine-type "n1-standard-1" --image-project "debian-cloud" --image "debian-9-stretch-v20190213" --subnet "default"

