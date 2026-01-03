# Task 3 – SQL Injection on DVWA (Low Security)

For this task, I demonstrated an SQL Injection vulnerability using the Damn Vulnerable Web Application (DVWA) with the security level set to low.
The goal was to exploit improper input validation and retrieve database records without proper authentication.

---

## 1. Objective

The main objective of this task was to understand how SQL Injection vulnerabilities occur in web applications.
By manipulating user input, it is possible to alter database queries and gain unauthorized access to sensitive information.

---

## 2. Environment and Tools Used

* Operating System: Kali Linux (VirtualBox)
* Web Application: DVWA (Damn Vulnerable Web Application)
* Database: MySQL / MariaDB
* Tools Used: Web Browser and curl

---

## 3. Setup and Configuration

### DVWA Installation

* Apache and MariaDB services were installed and started.
* DVWA was placed inside the `/var/www/html/` directory.
* Database credentials were configured in the `config.inc.php` file.

### Security Level Configuration

* Logged into DVWA using default credentials.
* Navigated to **DVWA Security**.
* Set the security level to **Low** and applied the changes.

This configuration makes the application intentionally vulnerable for testing purposes.

---

## 4. SQL Injection Attack Performed

### Vulnerable Input

The SQL Injection was performed on the **SQL Injection** module in DVWA, which accepts a User ID as input.

### Injection Payload Used

```
1' OR '1'='1
```

### Result of the Injection

* The injected payload bypassed the intended SQL query condition.
* Multiple user records were returned instead of a single result.
* User accounts such as `admin`, `Gordon`, `Hack`, and others were displayed.

This confirms that user input was directly used in SQL queries without validation.

---

## 5. Script File Used

To automate the exploitation process, a script named **sql_injection_exploit.sh** was created.

### Script Purpose

* Sends a crafted SQL Injection payload to the vulnerable DVWA endpoint.
* Uses an authenticated session cookie.
* Retrieves database output from the vulnerable page.

### Script Execution

Make the script executable:

```
chmod +x sql_injection_exploit.sh
```

Run the script:

```
./sql_injection_exploit.sh
```

---

## 6. Commands Used and Explanation

The following commands were used during the setup, exploitation, and verification of the SQL Injection vulnerability in DVWA.

### Start Apache Web Server

```bash
sudo systemctl start apache2
```

This command starts the Apache web server, which is required to host the DVWA application locally.

---

### Start MariaDB Database Server

```bash
sudo systemctl start mariadb
```

This command starts the database service used by DVWA to store user credentials and application data.

---

### Check Service Status

```bash
sudo systemctl status apache2
sudo systemctl status mariadb
```

These commands verify that both Apache and MariaDB services are running correctly.

---

### Access DVWA in Browser

```
http://127.0.0.1/DVWA/
```

This URL is used to open the DVWA application hosted on the local system.

---

### Set DVWA Security Level to Low

Performed through the DVWA web interface:

```
DVWA Security → Low → Submit
```

Setting the security level to low disables input validation and makes the application vulnerable for testing.

---

### SQL Injection Payload Execution

```
1' OR '1'='1
```

This payload manipulates the SQL query logic to always return true, resulting in multiple database records being displayed.

---

### Make the Exploit Script Executable

```bash
chmod +x sql_injection_exploit.sh
```

This command grants execution permission to the SQL Injection exploit script.

---

### Execute the SQL Injection Script

```bash
./sql_injection_exploit.sh
```

This command runs the script that sends the SQL Injection payload to the vulnerable DVWA endpoint and retrieves the output.

---

### View Apache Error Logs (Optional)

```bash
sudo tail -f /var/log/apache2/error.log
```

This command is used to monitor server-side logs during troubleshooting and verification.

---

## 7. Vulnerability Explanation

The vulnerability exists because:

* User input is not sanitized or validated.
* SQL queries are dynamically constructed using raw input.
* Prepared statements or parameterized queries are not implemented.

This allows attackers to manipulate SQL logic and access unauthorized data.

---

## 8. Mitigation and Fixes

To prevent SQL Injection attacks:

* Use prepared statements or parameterized queries.
* Validate and sanitize all user inputs.
* Implement proper error handling.
* Apply stricter security configurations in production environments.

---

## 9. Files Included

* **sql_injection_exploit.sh** – Script demonstrating the SQL Injection attack
* **Screenshots/** – DVWA setup, security level configuration, payload injection, and output results
* **Exploiting SQL Injection in DVWA (Low Security).mp4** – Screen recording of the SQL Injection process
* **README.md** – Documentation explaining the attack and vulnerability

---

## 10. Conclusion

This task demonstrated how SQL Injection vulnerabilities can compromise web application security when input validation is not enforced.
By exploiting the vulnerability in DVWA, multiple database records were retrieved without proper authorization.
This exercise highlights the importance of secure coding practices and proper input handling in web applications.


