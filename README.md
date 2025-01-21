# uv_python_package

UV offers a modern alternative to PIP and virtualenv by combining environment management and package installation into a single, faster tool. With its Rust-based implementation, UV significantly outperforms PIP in speed and memory usage while maintaining compatibility with the Python ecosystem. Its advantages include:

- **Performance:** 10–100x faster than PIP with parallel downloads and an optimized dependency resolver.
- **Efficiency:** Lower memory usage during installation and dependency resolution.
- **Error Handling:** Clearer error messages and better conflict resolution.
- **Reproducibility:** Lockfiles ensure consistent environments across systems.
- **Integration:** Seamless migration using existing `requirements.txt` files.

UV simplifies workflows and improves reliability, making it an appealing choice for modern Python development.

 
 
 ---
 
 
 structured guide tailored for **Windows** users working with **UV**:

---

### **Getting Started**

1. **Install UV**  
   Open PowerShell and run the following command to install UV:  
   ```powershell
   powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

2. **Initialize a New Project**  
   - **Create a New Project**:  
     ```powershell
     uv init <project-name>
     cd <project-name>
     ```
   - **Initialize in the Current Directory**:  
     ```powershell
     mkdir <project-name>
     cd <project-name>
     uv init
     ```

---

### **Project Structure**
A UV project typically includes the following:
```
.
├── .venv/               # Virtual environment folder
├── .python-version      # Specifies Python version
├── README.md            # Project description
├── pyproject.toml       # Project metadata and dependencies
├── uv.lock              # Dependency lockfile
└── hello.py             # Sample Python script
```

---

### **Managing Dependencies**

- **Add a Dependency**:  
  ```powershell
  uv add <package-name>
  ```
  Example:  
  ```powershell
  uv add requests
  uv add 'requests==2.31.0'
  ```

- **Remove a Dependency**:  
  ```powershell
  uv remove <package-name>
  ```

- **Upgrade a Dependency**:  
  ```powershell
  uv lock --upgrade-package <package-name>
  ```

---

### **Running Commands**

1. **Run a Script or Command**:  
   Use `uv run` to execute within the project environment:
   ```powershell
   uv run <script-or-command>
   ```
   Examples:
   - Run a Python script:  
     ```powershell
     uv run hello.py
     ```
   - Run a command (e.g., Flask server):  
     ```powershell
     uv add flask
     uv run -- flask run -p 3000
     ```

2. **Manually Activate the Environment**:  
   If you need to manually activate the virtual environment:
   ```powershell
   .venv\Scripts\activate
   ```
   Then, run your Python scripts or commands as usual:
   ```powershell
   python hello.py
   ```

---

### **Building Distributions**

1. **Build Project Distributions**:  
   Use the `uv build` command to create source and binary distributions:  
   ```powershell
   uv build
   ```
   Distributions will be stored in the `dist/` folder.

---

### **Next Steps**
1. **Explore More Features**:  
   - Check out UV’s [official documentation](https://astral.sh/uv/guide).
   - Learn about building and publishing projects.

2. **Try Additional Commands**:
   - Run checks using `ruff`:  
     ```powershell
     uv add ruff
     uv run ruff check
     ```

This guide should help you manage your projects with **UV** effectively on Windows!
