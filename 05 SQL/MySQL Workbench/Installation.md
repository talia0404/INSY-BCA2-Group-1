# **Step 1: Install MySQL Server**

## Option A: Use the MySQL Installer 

1. Go to the official MySQL Installer page:  
   [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)

2. Download the **MySQL Installer for Windows** (preferably the full version).

3. Run the installer.

4. **Choose Full Download version** during setup — this installs:
   - MySQL Server
   - MySQL Workbench
   - Other useful tools

5. During setup:
   - Choose port `3306` 
   - Set a password for the `root` user
   - You can leave default settings for most options

6. Finish the installation and configuration steps.

---

## **Step 2: Start the MySQL Server**

After installation:

- Open **Services** (`Win + R`, then type `services.msc`)
- Now you should see **MySQL** or **MySQL80** in the list
- Right-click > **Start**

---

## **Step 3: Go Back to MySQL Workbench**

- Open Workbench
- Create a new connection
  - Hostname: `localhost`
  - Port: `3306`
  - Username: `root`
  - Password: (enter the one you created during setup)

- Click **“Test Connection”** — it should now succeed.

---
