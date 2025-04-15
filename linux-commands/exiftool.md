# 📸 exiftool Cheatsheet

O `exiftool` é uma ferramenta extremamente poderosa para ler, editar e remover metadados de arquivos — especialmente imagens, vídeos, PDFs e documentos. Muito útil em CTFs de forense e steganografia.

---

## 📌 Sintaxe Básica

```bash
exiftool [opções] arquivo
```

Exemplo simples:

```bash
exiftool imagem.jpg
```

---

## 🔧 Exemplos Comuns

| Comando                        | Descrição                                                  |
|--------------------------------|-------------------------------------------------------------|
| `exiftool imagem.jpg`          | Mostra todos os metadados do arquivo                       |
| `exiftool -DateTimeOriginal imagem.jpg` | Mostra somente o campo de data original       |
| `exiftool -a -u -g1 imagem.jpg`| Mostra todos os grupos e tags desconhecidas                |
| `exiftool -json imagem.jpg`    | Mostra metadados no formato JSON                           |
| `exiftool -r pasta/`           | Analisa arquivos recursivamente                            |

---

## ✏️ Modificando Metadados

| Comando                                      | Descrição                                 |
|----------------------------------------------|--------------------------------------------|
| `exiftool -Author="CTF Hacker" arquivo.jpg`  | Define o autor                             |
| `exiftool -Comment="Flag escondida"`         | Adiciona comentário                        |
| `exiftool -All= arquivo.jpg`                 | Remove todos os metadados do arquivo       |
| `exiftool -overwrite_original -All= arquivo.jpg` | Remove e sobrescreve                      |

---

## 🧪 Casos Úteis em CTFs

- Buscar flags escondidas:
  ```bash
  exiftool imagem.jpg | grep -i flag
  ```

- Comparar dois arquivos:
  ```bash
  exiftool original.jpg > 1.txt
  exiftool modificado.jpg > 2.txt
  diff 1.txt 2.txt
  ```

- Extrair metadados de PDFs:
  ```bash
  exiftool report.pdf
  ```

---

## 🛠 Dicas

- Funciona com imagens (JPG, PNG, TIFF), vídeos (MP4, MOV), PDFs, DOCX, ZIP, etc.
- Pode ser usado com `-r` para varrer diretórios inteiros.
- Combine com `strings`, `file`, `binwalk` para análise completa.

---

## 🔚 Referências

- [https://exiftool.org](https://exiftool.org)
- `man exiftool`
