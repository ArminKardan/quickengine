# 📦 Publishing the Project in QE

Before publishing, ensure your project is fully functional in development mode. This is **mandatory** since all infrastructural updates are delivered to the project only during development mode.

---

## ✅ Step 1: Test in Development Mode

Run all blocks (`microservice`, `xwebsite`, and all `workers`) in development mode and verify their functionality.

---

## ⬆️ Step 2: Upload to GitHub

1. Run `push.exe` in the root of your project directory.
2. The script will upload the entire project to GitHub.
3. ⚠️ Make sure you have set your GitHub token correctly (as explained previously).

---

## 🔐 Step 3: Get Explore Secret Key

1. Open **Explore > Settings**.
2. Click on **"Secure Key"** or **"کلید امن"** and copy the key.

---

## 🔍 Step 4: Access the Publisher Service

1. In the **QE Services** panel, search for:  
   - `Service Publisher` or `منتشر کننده سرویس`
2. If you don't have it, click **"Get service"** or **"دریافت سرویس"**.
3. Once acquired, it will appear in [My Apps](https://qepal.com/fa/app).

---

## 📦 Step 5: Add Dependencies

If your project needs additional NPM packages:

- Use **"add npm library"** for regular dependencies (added to `dependencies`).
- Use **"add -D npm library"** for dev dependencies (added to `devDependencies`).

If your python worker needs additonal packages put their names in deploy window.

This replicates development behavior in production.

---

## 🧱 Step 6: Add and Deploy Blocks

1. In the publisher service, click **"Add block"** or **"اضافه کردن بلاک"**.
2. Paste the **Explore Secret Key**.
3. You will see a list of all blocks (GUI, workers, etc.).
4. Select the block you want to publish.
5. Repeat for other blocks (e.g., GUI and worker).

---

## 🚀 Step 7: Start Deployment

1. Open the desired block from the publisher.
2. Click **"Start Deploy"** or **"شروع دیپلوی"**.
3. The block will go online and be live to end users.

---

✅ You're all set! Your QE project is now published and running online.