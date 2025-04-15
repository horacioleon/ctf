# 🔁 uniq Cheatsheet

O comando `uniq` é usado para remover linhas duplicadas consecutivas de um arquivo ou entrada. É comumente usado em conjunto com `sort`.

---

## 📌 Sintaxe Básica

```bash
uniq [opções] [entrada] [saída]
```

Exemplo simples:

```bash
sort arquivo.txt | uniq
```

---

## 🔧 Exemplos Comuns

| Comando                                 | Descrição                                              |
|------------------------------------------|---------------------------------------------------------|
| `uniq arquivo.txt`                      | Remove duplicatas consecutivas                         |
| `sort arquivo.txt | uniq`               | Remove duplicatas (ordenação + `uniq`)                |
| `uniq -c arquivo.txt`                   | Mostra o número de ocorrências de cada linha           |
| `uniq -d arquivo.txt`                   | Mostra apenas linhas duplicadas                        |
| `uniq -u arquivo.txt`                   | Mostra apenas linhas únicas                            |
| `sort arquivo.txt | uniq -ci`           | Remove duplicatas ignorando case, e conta ocorrências  |

---

## 🧪 Casos Úteis em CTFs

- Contar IPs únicos em logs:
  ```bash
  awk '{print $1}' access.log | sort | uniq -c | sort -nr
  ```

- Verificar strings únicas em dump de memória:
  ```bash
  strings dump.bin | sort | uniq
  ```

- Listar comandos usados (bash history):
  ```bash
  sort ~/.bash_history | uniq -c | sort -nr
  ```

---

## 🛠 Dicas

- `uniq` **só funciona em linhas consecutivas duplicadas**, por isso o uso de `sort` é comum.
- Combine com `sort`, `awk`, `cut` ou `grep` para maior controle.

---

## 🔚 Referências

- `man uniq`
- `uniq --help`
- [explainshell.com](https://explainshell.com/)
