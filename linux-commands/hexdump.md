# 🧪 hexdump Cheatsheet

O comando `hexdump` exibe o conteúdo de arquivos em formato hexadecimal, com opções para personalizar o layout da saída. É útil em CTFs, engenharia reversa, e análise de dados binários.

---

## 📌 Sintaxe Básica

```bash
hexdump [opções] arquivo
```

Exemplo simples:

```bash
hexdump binario.bin
```

---

## 🔧 Exemplos Comuns

| Comando                       | Descrição                                                   |
|-------------------------------|--------------------------------------------------------------|
| `hexdump arquivo`             | Exibe conteúdo em hex e ASCII                               |
| `hexdump -C arquivo`          | Mostra saída estilo `xxd`, com ASCII no final                |
| `hexdump -n 64 arquivo`       | Lê apenas os primeiros 64 bytes                              |
| `hexdump -v -e '1/1 "%02X "'` | Mostra apenas os hex bytes, sem endereços ou ASCII           |
| `hexdump -e '16/1 "%02x " "\n"' arquivo` | Mostra 16 bytes por linha                               |

---

## 🧪 Casos Úteis em CTFs

- Ver magic bytes e estrutura de arquivos:
  ```bash
  hexdump -C arquivo.jpg | head
  ```

- Analisar alterações byte a byte:
  ```bash
  diff <(hexdump -C original.bin) <(hexdump -C modificado.bin)
  ```

- Extrair padrões ou strings codificadas:
  ```bash
  hexdump -C dump.bin | grep -i 'flag'
  ```

---

## 🛠 Dicas

- `-C` é a forma mais amigável para humanos (como `xxd`).
- Combine com `head`, `cut`, `grep`, `xxd`, `file`, `binwalk` para análise binária.
- Pode ser customizado com `-e` para layouts específicos (veja `man hexdump`).

---

## 🔚 Referências

- `man hexdump`
- [explainshell.com](https://explainshell.com/)
