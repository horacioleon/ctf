# 🧱 binwalk Cheatsheet

O `binwalk` é uma ferramenta poderosa para análise de arquivos binários, especialmente útil para detectar e extrair dados embutidos como firmwares, imagens, arquivos compactados, entre outros. Essencial em CTFs de forense e análise reversa.

---

## 📌 Sintaxe Básica

```bash
binwalk [opções] arquivo
```

Exemplo simples:

```bash
binwalk firmware.bin
```

---

## 🔧 Exemplos Comuns

| Comando                        | Descrição                                                       |
|--------------------------------|------------------------------------------------------------------|
| `binwalk arquivo.bin`          | Analisa o binário em busca de assinaturas conhecidas            |
| `binwalk -e arquivo.bin`       | Extrai automaticamente arquivos encontrados                     |
| `binwalk -Me arquivo.bin`      | Faz análise **recursiva** e extração de múltiplos níveis         |
| `binwalk -B arquivo.bin`       | Mostra entropia (picos indicam compressão ou criptografia)       |
| `binwalk -A arquivo.bin`       | Mostra strings ASCII em contexto                                 |
| `binwalk -D="png image" arquivo` | Extrai apenas arquivos de tipo especificado (ex: PNG)           |

---

## 🧪 Casos Úteis em CTFs

- Extração de imagens ou zip ocultos:
  ```bash
  binwalk -e desafio.bin
  ```

- Ver se o conteúdo está comprimido ou criptografado:
  ```bash
  binwalk -B desafio.bin
  ```

- Analisar firmwares ou dumps de ROM:
  ```bash
  binwalk -Me firmware.img
  ```

---

## 🛠 Dicas

- A flag `-e` cria uma pasta `_arquivo.bin.extracted/` com os conteúdos extraídos.
- Combine com `file`, `xxd`, `strings`, `foremost`, `exiftool` para investigação completa.
- Requer o pacote `binwalk`, e para extrações completas: `sudo apt install binwalk squashfs-tools`.

---

## 🔚 Referências

- [https://github.com/ReFirmLabs/binwalk](https://github.com/ReFirmLabs/binwalk)
- `man binwalk`
- `binwalk --help`
