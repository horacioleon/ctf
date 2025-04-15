# 🧾 file Cheatsheet

O comando `file` tenta identificar o tipo de conteúdo de um arquivo com base em sua assinatura mágica e metadados, e não apenas pela extensão. Muito útil em CTFs e análise forense.

---

## 📌 Sintaxe Básica

```bash
file [opções] arquivo
```

Exemplo simples:

```bash
file mystery.bin
```

---

## 🔧 Exemplos Comuns

| Comando                  | Descrição                                                  |
|--------------------------|-------------------------------------------------------------|
| `file arquivo`           | Detecta o tipo do arquivo                                  |
| `file *`                 | Mostra o tipo de todos os arquivos no diretório            |
| `file -i arquivo`        | Mostra o tipo MIME (ex: `text/plain`, `application/zip`)   |
| `file -b arquivo`        | Remove o nome do arquivo da saída                          |
| `file -L link`           | Segue links simbólicos                                     |
| `file -z arquivo.gz`     | Tenta analisar arquivos compactados                        |

---

## 🧪 Casos Úteis em CTFs

- Identificar arquivos sem extensão:
  ```bash
  file desafio
  ```

- Analisar dumps de memória:
  ```bash
  file core
  ```

- Identificar arquivos modificados:
  ```bash
  find . -type f -exec file {} \;
  ```

---

## 🛠 Dicas

- Útil para identificar PDFs renomeados, imagens sem extensão, executáveis mascarados, etc.
- Combine com `binwalk`, `xxd`, `hexdump`, `exiftool` para análises profundas.

---

## 🔚 Referências

- `man file`
- [explainshell.com](https://explainshell.com/)
