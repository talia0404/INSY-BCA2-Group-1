## 🔵 **Windows**

### 1. **Download the Installer**

* Go to the official MongoDB download page:
  [https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)
* Choose **Windows** and select the `.msi` installer.

### 2. **Run the Installer**

* Double-click the `.msi` file.
* Choose **Complete** setup.
* Check **Install MongoDB Compass** (optional GUI).
* Click **Install**.

### 3. **Add MongoDB to PATH**

* The installer does this automatically if you selected the option during installation.
* To verify: open **Command Prompt**, and type:

  ```bash
  mongod --version
  ```

### 4. **Start MongoDB**

* MongoDB installs as a Windows service.
* You can start it via:

  ```bash
  net start MongoDB
  ```

---

## 🟢 **macOS (Using Homebrew)**

### 1. **Install Homebrew** (if not already):

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2. **Tap MongoDB**

```bash
brew tap mongodb/brew
```

### 3. **Install MongoDB**

```bash
brew install mongodb-community@7.0
```

### 4. **Start MongoDB**

```bash
brew services start mongodb-community@7.0
```

---

## 🟡 **Ubuntu (Debian-based Linux)**

### 1. **Import the public key**

```bash
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg --dearmor
```

### 2. **Add the repository**

```bash
echo "deb [signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg] https://repo.mongodb.org/apt/ubuntu $(lsb_release -cs)/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```

### 3. **Update packages and install**

```bash
sudo apt update
sudo apt install -y mongodb-org
```

### 4. **Start and enable MongoDB**

```bash
sudo systemctl start mongod
sudo systemctl enable mongod
```

---

## ✅ **Check MongoDB Version**

```bash
mongod --version
```
