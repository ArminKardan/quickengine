# 📦 Installing Python Packages for `python-worker` in Development Mode

When working with `python-worker`, some external packages (like `Pillow` for image processing) are not installed by default. To use them during development, follow the steps below.

---

## 🛠️ Step-by-Step Installation

1. **Open Terminal in the Worker Directory**

   - Navigate to your `python-worker` folder.
   - Double-click the file named:  
     ```
     terminal.bat
     ```

   This launches a terminal with the correct environment and paths set.

2. **Install Your Package**

   - For example, to install **Pillow** (Python Imaging Library), type:
     ```bash
     pip install pillow
     ```

   - Alternatively, if you prefer to use **Conda** (and the package is available there):
     ```bash
     conda install pillow
     ```

3. **Use the Installed Package**

   After installation, you can import and use the package in your `python-worker` scripts:
   ```python
   from PIL import Image

   img = Image.open("example.jpg")
   img.show()
   ```

---

## ✅ Notes

- Packages installed this way are only available in **development mode**.
- When publishing the worker, you'll need to declare dependencies so they're available in production.
