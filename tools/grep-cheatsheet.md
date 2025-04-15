# 🔍 grep Cheatsheet

O `grep` é uma das ferramentas mais poderosas para busca de padrões em arquivos de texto no Linux. Este guia cobre usos básicos e avançados, incluindo exemplos úteis para CTFs e análise forense.

---

## 📌 Sintaxe Básica

```bash
grep [opções] "padrão" arquivo
```

---

## 🔧 Exemplos Comuns

| Comando                                  | Descrição                                                    |
|------------------------------------------|---------------------------------------------------------------|
| `grep "flag" arquivo.txt`                | Busca a palavra **flag** em `arquivo.txt`                     |
| `grep -i "flag" arquivo.txt`             | Busca ignorando **case** (FLAG, Flag, etc.)                   |
| `grep -r "flag" /caminho/`               | Busca **recursiva** em diretórios                             |
| `grep -n "flag" arquivo.txt`             | Mostra **número da linha** onde ocorre                        |
| `grep -v "flag" arquivo.txt`             | Mostra linhas que **não** contêm o padrão                     |
| `grep -c "flag" arquivo.txt`             | Conta quantas vezes o padrão aparece                          |
| `grep -A 3 "flag" arquivo.txt`           | Mostra 3 linhas **após** o match                              |
| `grep -B 2 "flag" arquivo.txt`           | Mostra 2 linhas **antes** do match                            |
| `grep -C 1 "flag" arquivo.txt`           | Mostra 1 linha antes e 1 linha depois (**contexto**)          |

---

## 🔍 Usos Avançados

### Buscar por múltiplas palavras

```bash
grep -E "admin|root|user" arquivo.txt
```

### Usar com `find`

```bash
find . -type f -exec grep -i "flag" {} +
```

### Extrair apenas o valor usando regex

```bash
grep -oE "flag\{[A-Za-z0-9_]+\}"
```

---

## 📁 Aplicações em CTFs

- **Busca de flags escondidas:** `grep -r "flag{" .`
- **Busca em `.pcap` convertidos:** `strings dump.txt | grep "flag"`
- **Busca por senhas comuns:** `grep -iE "pass(word)?|senha" dados.txt`
- **Filtragem de logs:** `grep -i "GET /admin" access.log`

---

## 🛠 Dica com `less` (highlight ao ler arquivos)

```bash
less +F arquivo.log
```

Pressione `/` e digite o termo que deseja buscar.

---

## ✅ Extra: Grep com cores

```bash
grep --color=always "padrão" arquivo.txt
```

---

## 🔚 Referências

- `man grep`
- `grep --help`
- [explainshell.com](https://explainshell.com/)
