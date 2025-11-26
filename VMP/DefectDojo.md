# Vulnerability Manament Platform
A Vulnerability Management Platform (VMP) is a centralized system that helps organizations identify, track, assess, prioritize, and remediate security vulnerabilities across their infrastructure, applications, and services.

Modern IT environments generate a large volume of findings from scanners such as SAST, DAST, SCA, cloud security tools, container scanners, and penetration tests. Without a structured process, these findings quickly become unmanageable, inconsistent, or lost.

Why Organizations Use Vulnerability Management Platforms:
- Reduce security risk and attack surface
- Improve visibility and control over vulnerabilities
- Support compliance and audit requirements
- Enable DevSecOps processes and shift-left security
- Standardize vulnerability lifecycle from detection to closure

A VMP is therefore a critical component of any mature cybersecurity program, ensuring that discovered vulnerabilities are not just detected — but actually managed and resolved.

## [DefectDojo](https://defectdojo.com/platform)
DefectDojo is an open-source Application Security Vulnerability Management Platform designed to help security teams handle large volumes of findings from different security tools in an organized and scalable way. 

DefectDojo provides a centralized place to:
- Import security scan results from dozens of tools (SAST, DAST, SCA, container scanners, cloud scanners, pen tests).
- Track vulnerabilities across products, projects, and releases.
- Deduplicate findings across different scans or tools to avoid noise.
- Enrich vulnerability data with severity, CWE, CVSS scores, endpoints, tags, owners, etc.
- Triage, assign, and manage remediation directly within the platform.
- Generate reports and dashboards for leadership, developers, and auditors.
- Integrate with CI/CD pipelines via a fully featured REST API.


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

After the setup you should be able to access the dashboard

-> [localhost:8080](http://localhost:8080/dashboard)

### Importing Results
1. Log in to DefectDojo (at http://localhost:8080).

2. Navigate to: Products → Add Product

3. Navigate to: Engagements -> Finidings -> Import Scan Results
    - Select your file: zap_results.xml

4. Choose the scan type: Scan Type “ZAP Scan”

6. Click Upload / Submit.

DefectDojo will parse the findings and create a Test containing all ZAP vulnerabilities.

-> [Official Import Documentation](https://docs.defectdojo.com/en/connecting_your_tools/import_scan_files/import_scan_ui/)
