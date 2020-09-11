1. Connect

```
gcloud auth login
```

2. Set project

```
gcloud config set project qwiklabs-gcp-02-0a9XXXX
```
qwiklabs-gcp-02-0a9XXXX is the GCP Project ID

3. Start Kubernetes Clusters

```bash
gcloud container clusters create webfrontend --zone us-central1-a --num-nodes 2
```

4. Generate an entry kubeconfig
gcloud container clusters get-credentials cluster-name

5. Generate kubeconfig 

gcloud container clusters get-credentials 

6. 
