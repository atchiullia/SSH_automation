
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
