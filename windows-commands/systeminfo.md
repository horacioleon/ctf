


# 🖥️ systeminfo

O comando `systeminfo` exibe informações detalhadas sobre o sistema operacional, hardware e atualizações instaladas.

---

## 📋 Sintaxe Básica

```powershell
systeminfo
```

---

## 📌 Informações Obtidas

- Nome do host
- Versão do sistema operacional
- Build do Windows
- Fabricante e modelo do sistema
- Tipo de BIOS
- Memória física instalada e disponível
- Hotfixes instalados
- Configurações de rede

---

## ⚡ Exemplo de Saída

```plaintext
Host Name:                 WIN-CTF01
OS Name:                   Microsoft Windows Server 2019 Datacenter
OS Version:                10.0.17763 N/A Build 17763
System Manufacturer:       VMware, Inc.
System Model:              VMware Virtual Platform
BIOS Version:              Phoenix Technologies LTD 6.00, 7/2/2015
Total Physical Memory:     4,095 MB
Available Physical Memory: 2,000 MB
Hotfix(s):                 5 Hotfix(s) Installed.
```

---

## 🎯 Dicas para CTF e Pentest

- Verificar a versão do sistema para explorar vulnerabilidades conhecidas.
- Identificar máquinas virtuais (ex: VMware, VirtualBox).
- Encontrar hotfixes ausentes que podem indicar falhas de segurança.

---