# Vulnerability Manament Platform
## DefectDojo


-> [Official Documentation](https://docs.defectdojo.com/en/open_source/installation/configuration/)

### Setup
#### 1. Clone Repository
```
user@demo[/dev-sec-ops-demos]$ git clone https://github.com/DefectDojo/django-DefectDojo.git
```
```
user@demo[/dev-sec-ops-demos]$ cd django-DefectDojo
```
#### 2. (Optional) Check if Docker Compose is compatible
```
user@demo[/dev-sec-ops-demos]$ ./docker/docker-compose-check.sh
```
#### 3. Build Docker images
```
user@demo[/dev-sec-ops-demos]$ docker compose build
```
#### 4. Start container
```
user@demo[/dev-sec-ops-demos]$ docker compose up -d
```
#### 5. Wait until the initializer is finished.
After that, you can retrieve the automatically generated admin password from the logs:
```
user@demo[/dev-sec-ops-demos]$ docker compose logs initializer | grep "Admin password:"
```

### UI
After the setup you should be able to access the dashboard

-> [localhost:8080](http://localhost:8080/dashboard)

### Importing Findings
1. Log in to DefectDojo (at http://localhost:8080).

2. Navigate to: Products → Add Product

3. Navigate to: Engagements -> Finidings -> Import Scan Results
    - Select your file: zap_results.xml

4. Choose the scan type: Scan Type “ZAP Scan”

6. Click Upload / Submit.

DefectDojo will parse the findings and create a Test containing all ZAP vulnerabilities.

-> [Official Import Documentation](https://docs.defectdojo.com/en/connecting_your_tools/import_scan_files/import_scan_ui/)
