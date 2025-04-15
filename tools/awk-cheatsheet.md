# 🧠 awk Cheatsheet

O `awk` é uma linguagem de processamento de texto muito poderosa para análise de logs, arquivos CSV, e manipulação de texto em geral — essencial em CTFs e forense.

---

## 📌 Sintaxe Básica

```bash
awk 'padrão {ação}' arquivo
```

---

## 🔧 Exemplos Comuns

| Comando                                      | Descrição                                                  |
|----------------------------------------------|-------------------------------------------------------------|
| `awk '{print $1}' arquivo.txt`               | Mostra a **primeira coluna**                               |
| `awk '{print $1, $3}' arquivo.txt`           | Mostra a **coluna 1 e 3**                                   |
| `awk '/admin/ {print $0}' arquivo.txt`       | Mostra linhas que **contêm 'admin'**                       |
| `awk 'NR==5' arquivo.txt`                    | Mostra apenas a **quinta linha**                           |
| `awk 'NF > 3' arquivo.txt`                   | Linhas com **mais de 3 campos**                            |
| `awk '{sum += $2} END {print sum}'`          | Soma todos os valores da **coluna 2**                      |

---

## 🧪 Filtros Frequentes

### Apenas linhas que contêm "flag"

```bash
awk '/flag/' arquivo.txt
```

### Mostrar linhas entre duas palavras

```bash
awk '/início/,/fim/' arquivo.txt
```

### Linhas com exatamente 3 colunas

```bash
awk 'NF==3' arquivo.txt
```

---

## 📁 Aplicações em CTFs

- Análise de logs: `awk '{print $1, $7}' access.log`
- Extração de IPs: `awk '{print $1}' access.log | sort | uniq -c | sort -nr`
- Processamento de CSV: `awk -F, '{print $2}' arquivo.csv`
- Conversão de bytes: `awk '{sum+=$1} END {print sum/1024 " KB"}'`

---

## 🛠 Dicas

- `$0` → linha inteira
- `$1`, `$2` ... → colunas
- `NR` → número da linha
- `NF` → número de colunas (fields)
- `BEGIN {}` → executado antes da leitura
- `END {}` → executado após a leitura

---

## ✅ awk em linha única

```bash
awk '{if ($3 > 50) print $1, $3}' arquivo.txt
```

---

## 🔚 Referências

- `man awk`
- [awk sandbox online](https://awk.js.org/)
- [explainshell.com](https://explainshell.com/)
