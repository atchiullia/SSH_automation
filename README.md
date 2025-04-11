# 🔐 Automated SSH Key Creation Script for Windows (PowerShell)

This project contains a PowerShell script that automates **the entire SSH key setup** process on Windows, including:

- Automatic elevation to administrator  
- Installation of OpenSSH Client and Agent (if needed)  
- Activation and startup of the `ssh-agent` service  
- Creation of the `.ssh` folder  
- Generation of a new `ed25519` key (if not present)  
- Addition of the private key to the agent  
- Automatic copy of the public key to the clipboard  

> Perfect for quickly configuring development environments or CI/CD pipelines.

---

## ⚙️ Requirements

- Windows 10 or later  
- PowerShell 5.1 or later  
- Permission to run scripts (`Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` if needed)

---

## 🚀 How to Use

1. **Clone or download this repository.**

2. **Run the script using PowerShell:**

```powershell
.\setup-ssh.ps1
```

> ⚠️ The script will automatically relaunch itself with elevated permissions if needed.

3. **After execution:**
   - The key will be generated (if not present)
   - Added to the SSH agent
   - And the public key will be copied to your clipboard

4. **Paste the key into GitHub:**  
   [https://github.com/settings/keys](https://github.com/settings/keys)

---

## 📁 Structure

```bash
📦 ssh-automation
 ┣ 📄 setup-ssh.ps1      # Main script
 ┗ 📄 README.md          # Documentation
```

---

## 💻 Script Behavior

- ✅ Checks for Admin privileges  
- 🧰 Installs and configures OpenSSH  
- 🔐 Generates `id_ed25519` key  
- 🧠 Prevents duplicate key generation  
- 📋 Automatically copies public key

---

## 📌 Example Output

```text
Running as administrator. Continuing script
Installing OpenSSH.Client~~~~0.0.1.0...
Configuring ssh-agent
Generating new SSH key
Adding key to ssh-agent: id_ed25519
Public key copied to clipboard.
Paste your new SSH key into GitHub
https://github.com/settings/keys
```

---

## 🧪 Tested On

- Windows 11 Home and Pro  
- PowerShell 5.1 and 7.x  
- Git Bash (partial support)

---

## 🛠️ Customization

Edit this line to use your email:

```powershell
ssh-keygen -t ed25519 -f $privateKeyPath -C "youremail@email.com"
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## ✨ Contributions

Feel free to open issues, submit PRs, or suggest improvements! 🚀  
You can contribute with:

- Linux/macOS support  
- Generation of multiple keys with custom names  
- GUI (Graphical Interface) creation

---

## 🤝 Credits

Created with ❤️ by Giullia
