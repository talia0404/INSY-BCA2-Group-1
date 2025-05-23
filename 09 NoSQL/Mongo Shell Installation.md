## ✅ Option 1: Check if `mongosh` is Installed

### A. Look in the Default MongoDB Folder:

Open File Explorer and navigate to:

```
C:\Program Files\MongoDB\Server\8.0\bin
```

Look for a file called `mongosh.exe`.

> If you find it, continue to **Step 2 below to add it to your PATH**.

---

## ✅ Option 2: Download `mongosh` Manually

If `mongosh.exe` is not in the folder, download it:

1. Go to: [https://www.mongodb.com/try/download/shell](https://www.mongodb.com/try/download/shell)
2. Choose:

   * **Version:** Latest
   * **OS:** Windows
   * **Package:** ZIP
3. Download and extract it.
4. Inside the extracted folder, you'll see `mongosh.exe`.

---

## ✅ Step 2: Add `mongosh` to System PATH (if needed)

1. Press `Win + S`, type **"environment variables"**, and open **"Edit the system environment variables"**.

2. Click **Environment Variables**.

3. Under **System Variables**, select `Path`, then click **Edit**.

4. Click **New** and add the path to your `mongosh.exe`, e.g.:

   ```
   C:\Program Files\MongoDB\Server\8.0\bin
   ```

   or

   ```
   C:\path\to\mongosh\bin
   ```

5. Click **OK** on all dialogs.

6. Close all open Command Prompt windows, open a new one, and run:

   ```bash
   mongosh
   ```

---

