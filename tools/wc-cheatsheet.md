# 📏 wc Cheatsheet

O comando `wc` (word count) é utilizado para contar linhas, palavras, bytes e caracteres em arquivos ou na entrada padrão. É simples, mas extremamente útil para análises rápidas em CTFs e scripts.

---

## 📌 Sintaxe Básica

```bash
wc [opções] [arquivo]
```

Exemplo simples:

```bash
wc arquivo.txt
```

---

## 🔧 Exemplos Comuns

| Comando               | Descrição                                      |
|------------------------|------------------------------------------------|
| `wc arquivo.txt`      | Mostra linhas, palavras e bytes                |
| `wc -l arquivo.txt`   | Conta apenas **linhas**                        |
| `wc -w arquivo.txt`   | Conta apenas **palavras**                      |
| `wc -c arquivo.txt`   | Conta apenas **bytes**                         |
| `wc -m arquivo.txt`   | Conta apenas **caracteres (UTF-8 aware)**      |
| `cat arquivo.txt \| wc -l` | Conta linhas da saída de outro comando     |

---

## 🧪 Casos Úteis em CTFs

- Contar linhas de código/funções:
  ```bash
  grep -r "function" . | wc -l
  ```

- Contar quantas flags ou ocorrências de uma palavra:
  ```bash
  grep -o "flag{" dump.txt | wc -l
  ```

- Contar strings extraídas de binário:
  ```bash
  strings bin | wc -l
  ```

---

## 🛠 Dicas

- `-l` = lines  
- `-w` = words  
- `-c` = bytes  
- `-m` = chars (diferente de `-c` em arquivos com UTF-8 multibyte)  
- Combine com `grep`, `awk`, `cut`, `strings`, etc.

---

## 🔚 Referências

- `man wc`
- `wc --help`
- [explainshell.com](https://explainshell.com/)
