

# 📚 Windows Commands Cheatsheets

Este diretório contém uma coleção de cheatsheets para comandos Windows Server organizados por categorias, com foco em CTFs, forense digital e segurança ofensiva.

---

### 🗂️ Índice por Categoria

#### 🖥️ Informações do Sistema
- `systeminfo`
- `hostname`
- `whoami`
- `wmic`

#### 👥 Usuários e Grupos
- `net user`
- `net localgroup`
- `Get-LocalUser`
- `Get-LocalGroupMember`

#### 🌐 Rede
- `ipconfig`
- `netstat`
- `netsh`
- `Get-NetIPAddress`

#### ⚙️ Processos e Serviços
- `tasklist`
- `sc`
- `Get-Service`

#### 📂 Arquivos e Permissões
- `dir`
- `icacls`
- `Get-Acl`

#### ⚡ PowerShell Essentials
- `Get-ExecutionPolicy`
- `Set-ExecutionPolicy`
- `Get-Command`
- `Import-Module`

#### 🛡️ Persistência
- `schtasks`
- `reg query`
- `Get-ScheduledTask`

---

## 🧩 Exemplos de Uso Rápido

```powershell
# Informações do sistema
systeminfo

# Enumerar todos os usuários
net user

# Mostrar IPs da máquina
ipconfig /all

# Ver processos rodando
tasklist /v

# Buscar tarefas agendadas
schtasks /query /fo LIST /v
```

---

> 📢 *Este material é para uso educacional e práticas em segurança ofensiva (CTF, Red Team, Pentest).*