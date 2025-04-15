# 🔢 sort Cheatsheet

O comando `sort` é utilizado para ordenar linhas de texto em arquivos ou na saída padrão. É uma ferramenta essencial para manipulação de dados em shell scripts e CTFs.

---

## 📌 Sintaxe Básica

```bash
sort [opções] [arquivo]
```

Exemplo simples:

```bash
sort nomes.txt
```

---

## 🔧 Exemplos Comuns

| Comando                                 | Descrição                                                   |
|------------------------------------------|--------------------------------------------------------------|
| `sort arquivo.txt`                      | Ordena linhas em ordem alfabética                           |
| `sort -r arquivo.txt`                   | Ordena em ordem **reversa**                                 |
| `sort -n numeros.txt`                   | Ordena numericamente                                        |
| `sort -k 2 arquivo.txt`                 | Ordena baseado na **segunda coluna**                        |
| `sort -u arquivo.txt`                   | Remove duplicatas (equivalente a `sort | uniq`)             |
| `sort -t ":" -k 2 arquivo.txt`          | Usa `:` como delimitador de campo e ordena pela 2ª coluna   |

---

## 🧪 Casos Úteis em CTFs

- Ordenar IPs por frequência:
  ```bash
  awk '{print $1}' access.log | sort | uniq -c | sort -nr
  ```

- Analisar strings mais comuns:
  ```bash
  strings dump.bin | sort | uniq -c | sort -nr
  ```

- Ordenar flags por ordem de descoberta:
  ```bash
  cat flags.txt | sort
  ```

---

## 🛠 Dicas

- `-n` → ordenação numérica
- `-r` → ordem reversa
- `-k N` → ordena pela N-ésima coluna
- `-t` → define delimitador de campo
- Combine com `uniq`, `cut`, `awk`, `grep` para maior controle

---

## 🔚 Referências

- `man sort`
- `sort --help`
- [explainshell.com](https://explainshell.com/)
