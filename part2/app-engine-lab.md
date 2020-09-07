1. Log on the account

```bash
gcloud auth login
```
2. Define project

```bash
gcloud config set project qwiklabs-gcp-02-0a9XXXX
```

3. Initialize App Engine

```bash
gcloud app create --project=qwiklabs-gcp-02-a18e49fc0207
```

When prompted we select the region where we want the App Engine Application located

4. Clone the source code

```bash
git clone https://github.com/GoogleCloudPlatform/python-docs-samples
```
5. Naviguer le dossier de la source

```bash
cd python-docs-samples/appengine/standard_python3/hello_world
```
6. Run the application locally

```bash
sudo apt update 
```

7. Set up virtual environnement for Python

```bash
sudo apt install virtualenv

virtualenv -p python3 venv
```

8. Activate the virtual environment

```bash
source venv/bin/activate
```

9. Navigate the project and install dependencies

```bash
pip install -r requirements.txt
```

10. Run the app

```bash
python main.py
```

11. Preview the app

http://localhost:8080


### Task 3: Deploy and run Hello World on App Engine ###

Navigate the source directory

```bash
cd ~/python-docs-samples/appengine/standard_python3/hello_world
```

Deploy the app

```bash
gcloud app deploy
```

Launc the browser

```bash
gcloud app browse
```

