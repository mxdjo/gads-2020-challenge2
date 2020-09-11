0. Connect to Gcloud account and set project

```bash
gcloud auth login
```

There is a page which will open and we will put the credentials.

Then we set the project

```bash
gcloud config set project PROJECT_ID
```

1. Create a VM instance name bloghost with startup script

gcloud compute instances create "bloghost" --machine-type "n1-standard-1" --image-project "debian-cloud" --image "debian-9-stretch-v20190312" --subnet "default" --metadata-from-file startup-script=lamp-install-script.sh --tags=http-server

The content of the startup script is the following:

apt-get update &&
apt-get install apache2 php php-mysql -y &&
service apache2 restart

gcloud compute --project=qwiklabs-gcp-00-245e8b75b699 firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server


2. Create a cloud Storage bucket using the gsutil command line

Then make a bucket named after our project ID

```bash
gsutil mb -p qwiklabs-gcp-04-3c631b0-l US gs://$DEVSHELL_PROJECT_ID
```

3. Retrieve the banner from a publicly accessible Storage location
gsutil cp gs://cloud-training/gcpfci/my-excellent-blog.png my-excellent-blog.png

4. Copy the banner image to the newly bucket
gsutil cp my-excellent-blog.png gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png

5. Modify the ACL of object

gsutil acl ch -u allUsers:R gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png


Task: Create the Cloud SQL Instance

1. Create the SQL instance
gcloud sql instances create NAME_OF_INSTANCE --zone=us-central1-a --root-password=MY_SUPER_PASSWORD

2. Create the DB user
gcloud sql users create USERNAME --instance=INSTANCE --password=XXXXX

In our case, the username is blogdbuser
the instance is blog-db
