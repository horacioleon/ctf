# 🔤 strings Cheatsheet

O comando `strings` é usado para extrair sequências de texto legível (ASCII ou Unicode) de arquivos binários. É especialmente útil para análise de malware, engenharia reversa e CTFs.

---

## 📌 Sintaxe Básica

```bash
strings [opções] arquivo
```

Exemplo simples:

```bash
strings executavel.bin
```

---

## 🔧 Exemplos Comuns

| Comando                      | Descrição                                                      |
|------------------------------|-----------------------------------------------------------------|
| `strings arquivo`            | Extrai todas as strings padrão (mín. 4 caracteres)              |
| `strings -n 6 arquivo`       | Extrai strings com no mínimo 6 caracteres                      |
| `strings -t x arquivo`       | Mostra o **offset hexadecimal** onde a string aparece          |
| `strings -e l arquivo`       | Extrai strings em **Unicode little-endian**                    |
| `strings -a arquivo`         | Examina o arquivo **inteiro**, não apenas seções de dados      |
| `strings -f *`               | Mostra o nome do arquivo antes da string (útil em múltiplos)   |

---

## 🧪 Casos Úteis em CTFs

- Buscar flags escondidas:
  ```bash
  strings binario | grep "flag"
  ```

- Extrair comandos de shell embutidos:
  ```bash
  strings exploit | grep "/bin"
  ```

- Analisar dumps de memória:
  ```bash
  strings core.dump > strings.txt
  ```

- Combinar com hexdump para contexto:
  ```bash
  xxd -c 16 bin | less
  ```

---

## 🛠 Dicas

- Strings ocultas podem estar em encoding alternativo → tente `-e l`, `-e b`, etc.
- Combine com `grep`, `sort`, `uniq`, `awk`, `cut` para análises mais ricas.
- Muito útil em arquivos como `.bin`, `.so`, `.exe`, `.jpg`, `.core`, etc.

---

## 🔚 Referências

- `man strings`
- [explainshell.com](https://explainshell.com/)
