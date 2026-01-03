# Task 2 – Basic Firewall Configuration Using UFW

For this task, I configured a basic firewall on my Kali Linux system using UFW (Uncomplicated Firewall).  
The goal was to enable the firewall, allow SSH traffic, deny HTTP traffic, and verify that the rules were applied correctly.

---

## 1. Objective
The main objective of this task was to understand how to control incoming network connections using UFW.  
By allowing only required ports and blocking unnecessary ones, the system becomes more secure and less exposed to attacks.

---

## 2. Commands Used

### Install UFW
sudo apt install ufw

### Enable the firewall
sudo ufw enable

### Allow SSH (Port 22)
sudo ufw allow ssh

### Deny HTTP (Port 80)
sudo ufw deny http

### Check firewall status and verify rules
sudo ufw status verbose

---

## 3. Firewall Configuration Summary

After running the above commands, UFW displayed the following expected results:

### • Port 22/tcp – ALLOW
- SSH traffic is permitted.
- SSH must remain open for secure remote administration.

### • Port 80/tcp – DENY
- HTTP traffic is blocked.
- This prevents unintentional web access or exposure of HTTP services.

Other observations:
- UFW was successfully enabled and active.
- The rules were applied correctly without conflicts.
- The default outgoing policy remained allowed, keeping the system functional.

---

## 4. Script File Used

I created a script named **ufw_configuration.sh** to automate all firewall steps.

### Script content:
sudo ufw enable
sudo ufw allow ssh
sudo ufw deny http
sudo ufw status


I made it executable using:
chmod +x ufw_configuration.sh

Then ran it using:
bash ufw_configuration.sh

---

## 5. Files Included
- **ufw_configuration.sh** – Script containing firewall commands.  
- **Screenshots/** – UFW enable, allow SSH, deny HTTP, and final status screenshot.  
- **Task 2 Demo Video.mp4** – Shows the commands being executed.  
- **README.md** – Explanation of the task and configuration steps.

---

## 6. Conclusion
This task helped me understand how to use UFW to manage basic firewall rules on a Linux system.  
By enabling the firewall, allowing SSH, and blocking HTTP, I learned how to control which connections are permitted.  
UFW provides a simple and effective way to improve system security with minimal commands.
