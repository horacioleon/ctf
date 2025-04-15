# 🔎 find Cheatsheet

O comando `find` é uma ferramenta poderosa do Linux para buscar arquivos e diretórios com base em diversos critérios. Muito útil em CTFs, forense e automação de tarefas.

---

## 📌 Sintaxe Básica

```bash
find [caminho] [opções] [expressão]
```

Exemplo simples:

```bash
find . -name "flag.txt"
```

---

## 🔧 Exemplos Comuns

| Comando                                      | Descrição                                                    |
|----------------------------------------------|---------------------------------------------------------------|
| `find . -name "*.txt"`                       | Encontra todos os arquivos `.txt`                            |
| `find /etc -type f -name "passwd"`           | Busca arquivo com nome "passwd" em `/etc`                    |
| `find . -type d -name "backup"`              | Busca diretórios com nome "backup"                           |
| `find . -size +10M`                          | Arquivos com mais de 10MB                                    |
| `find . -size -100k`                         | Arquivos com menos de 100KB                                  |
| `find . -mtime -1`                           | Arquivos modificados nas últimas 24h                         |
| `find . -perm 777`                           | Arquivos com permissão 777                                   |
| `find . -user root`                          | Arquivos pertencentes ao usuário root                        |
| `find . -empty`                              | Arquivos ou diretórios vazios                                |
| `find . -exec rm {} \;`                      | Executa comando para cada resultado (ex: deletar arquivos)   |

---

## 🧪 Casos Úteis em CTFs

- Encontrar arquivos ocultos:

  ```bash
  find . -name ".*"
  ```

- Listar arquivos com extensão `.bak`, `.swp`, etc:

  ```bash
  find . -regex ".*\\.(bak|swp|old)$"
  ```

- Buscar arquivos acessíveis globalmente:

  ```bash
  find / -perm -o=r 2>/dev/null
  ```

- Buscar executáveis SUID (privilégio de root):

  ```bash
  find / -perm -4000 -type f 2>/dev/null
  ```

---

## 🛠 Dicas Rápidas

- `-type f` → apenas arquivos  
- `-type d` → apenas diretórios  
- `-iname` → ignora capitalização  
- `-exec CMD {} \;` → executa comando em cada resultado  
- `2>/dev/null` → suprime mensagens de erro (permissão)

---

## 🔚 Referências

- `man find`
- `find --help`
- [explainshell.com](https://explainshell.com/)
