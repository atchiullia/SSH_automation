
# 🔐 Script de Automação de Criação de Chaves SSH no Windows (PowerShell)

Este projeto contém um script em PowerShell que automatiza **toda a configuração de chaves SSH** no Windows, incluindo:

- Elevação automática para administrador  
- Instalação do OpenSSH Client e Agent (se necessário)  
- Ativação e inicialização do serviço `ssh-agent`  
- Criação da pasta `.ssh`  
- Geração de nova chave `ed25519` (se não existir)  
- Adição da chave privada ao agente  
- Cópia automática da chave pública para a área de transferência  

> Ideal para configurar rapidamente o ambiente de desenvolvimento ou pipelines de CI/CD.

---

## ⚙️ Requisitos

- Windows 10 ou superior  
- PowerShell 5.1 ou superior  
- Permissão para executar scripts (`Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` se necessário)

---

## 🚀 Como usar

1. **Clone ou baixe este repositório.**

2. **Execute o script com PowerShell:**

```powershell
.\setup-ssh.ps1
```

> ⚠️ O script se relança automaticamente com permissões elevadas, se necessário.

3. **Após a execução:**
   - A chave será gerada (caso não exista)
   - Adicionada ao agente SSH
   - E a chave pública estará na sua área de transferência

4. **Cole a chave no GitHub:**  
   [https://github.com/settings/keys](https://github.com/settings/keys)

---

## 📁 Estrutura

```bash
📦 ssh-automation
 ┣ 📄 setup-ssh.ps1      # Script principal
 ┗ 📄 README.md          # Documentação
```

---

## 💻 Comportamento do script

- ✅ Verifica se está rodando como Admin  
- 🧰 Instala e configura o OpenSSH  
- 🔐 Gera chave `id_ed25519`  
- 🧠 Evita geração duplicada de chave  
- 📋 Copia a chave pública automaticamente

---

## 📌 Exemplo de uso

```text
Rodando como administrador. Continuando script
Instalando OpenSSH.Client~~~~0.0.1.0...
Configurando ssh-agent
Gerando nova chave SSH
Adicionando chave ao ssh-agent: id_ed25519
Chave publica copiada para a area de transferencia.
Cole no GitHub a sua nova chave SSH
https://github.com/settings/keys
```

---

## 🧪 Testado em

- Windows 11 Home e Pro  
- PowerShell 5.1 e 7.x  
- Git Bash (parcial)

---

## 🛠️ Personalização

Edite esta linha para usar seu e-mail:

```powershell
ssh-keygen -t ed25519 -f $privateKeyPath -C "seuemail@email.com"
```

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

## ✨ Contribuições

Sinta-se à vontade para abrir issues, enviar PRs ou sugerir melhorias! 🚀  
Você pode contribuir com:

- Suporte a Linux/macOS  
- Geração de múltiplas chaves com nomes customizados  
- Criação de interface gráfica (GUI)

---

## 🤝 Créditos

Criado com ❤️ por Giullia


---

# 🔐 SSH Key Automation Script

This PowerShell script automates the entire setup of SSH keys on Windows. It checks for administrator privileges, installs required OpenSSH components, generates a new SSH key if necessary, adds the private key to the SSH agent, and copies the public key to the clipboard—ready to be added to GitHub.

## 🚀 Features

- Automatically checks for administrator rights and elevates if needed
- Installs **OpenSSH Client** and **OpenSSH Agent** if not installed
- Enables and starts the `ssh-agent` service
- Creates `.ssh` folder if it doesn't exist
- Checks for existing SSH key pairs
- Generates an SSH key using the **ed25519** algorithm if no keys are found
- Adds the private key to the `ssh-agent`
- Copies the public key to clipboard for quick use on platforms like GitHub

## 📦 How to Use

1. **Open PowerShell as Administrator**
2. **Run the script:**

   ```powershell
   .\setup-ssh.ps1
   ```

3. If you already have SSH keys, it will use them.
4. If not, it will generate a new one and copy the public key to your clipboard.

## 🔧 Requirements

- Windows 10 or later
- PowerShell
- Admin privileges
- Internet access to install optional components if needed

## 📋 After Setup

Paste your copied public key into your GitHub SSH settings:

👉 https://github.com/settings/keys

## 📁 File Structure

```text
.
└── setup-ssh.ps1
```

## 🤖 Automates:

- Checking admin rights
- Installing OpenSSH features
- Running `ssh-keygen`
- Starting and configuring `ssh-agent`
- Adding private keys
- Copying public key

---

🛠 This tool was built to save time and avoid repetitive setup on new systems or virtual machines.

---

## 📜 License

MIT

