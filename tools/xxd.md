# 🧬 xxd Cheatsheet

O comando `xxd` converte arquivos binários em representações hexdump (hexadecimal + ASCII) e também pode reverter um hexdump para binário. É útil em engenharia reversa, forense e CTFs.

---

## 📌 Sintaxe Básica

```bash
xxd [opções] [arquivo]
```

Exemplo simples:

```bash
xxd arquivo.bin
```

---

## 🔧 Exemplos Comuns

| Comando                     | Descrição                                                   |
|-----------------------------|--------------------------------------------------------------|
| `xxd arquivo.bin`           | Mostra o hexdump (hexadecimal + ASCII)                      |
| `xxd -p arquivo.bin`        | Mostra só os bytes hexadecimais (sem ASCII nem endereços)   |
| `xxd -r dump.hex`           | Converte um hexdump de volta para binário                   |
| `xxd -r -p hex.txt`         | Reverte um hex plano para binário                           |
| `xxd -c 8 arquivo.bin`      | Mostra 8 bytes por linha                                    |
| `xxd -g 1 arquivo.bin`      | Agrupa por byte (útil para ver valor exato de cada byte)    |

---

## 🧪 Casos Úteis em CTFs

- Ver conteúdo oculto em binários:

  ```bash
  xxd arquivo.jpg | less
  ```

- Criar shellcode manual em hex:

  ```bash
  echo -ne "\\x90\\x90\\xcc" | xxd
  ```

- Reverter payloads hexadecimais:

  ```bash
  cat payload.hex | xxd -r -p > payload.bin
  ```

- Comparar binários:

  ```bash
  diff <(xxd file1.bin) <(xxd file2.bin)
  ```

---

## 🛠 Dicas

- `xxd` é bidirecional: pode tanto gerar quanto reverter hex.
- Combine com `cut`, `grep`, `less`, `file`, `hexdump` para análises mais avançadas.
- Para ver apenas os hex bytes (sem ASCII e endereços): `xxd -p`.

---

## 🔚 Referências

- `man xxd`
- [explainshell.com](https://explainshell.com/)
