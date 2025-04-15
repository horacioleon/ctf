# 📚 Linux Commands Cheatsheets

Este diretório contém uma coleção de cheatsheets para comandos Linux organizados por categorias, com foco em uso prático em CTFs, forense digital e segurança ofensiva.

---

## 📂 Índice por Categoria

### 🔍 Análise de Arquivos Binários
- [`file`](./file.md) — Identifica o tipo de arquivo
- [`xxd`](./xxd.md) — Visualiza conteúdo em hexadecimal
- [`hexdump`](./hexdump.md) — Alternativa ao xxd com saída customizável
- [`binwalk`](./binwalk.md) — Detecta e extrai dados embutidos
- [`exiftool`](./exiftool.md) — Lê e edita metadados

### 🧰 Manipulação de Texto
- [`grep`](./grep.md) — Busca padrões
- [`awk`](./awk.md) — Processamento por colunas
- [`sed`](./sed.md) — Substituição e edição in-place *(a criar)*
- [`cut`](./cut.md) — Recorta campos/colunas *(a criar)*
- [`sort`](./sort.md) — Ordenação de linhas
- [`uniq`](./uniq.md) — Remove duplicatas
- [`wc`](./wc.md) — Conta linhas, palavras e bytes

### 📥 Extração e Strings
- [`strings`](./strings.md) — Extrai texto legível de arquivos binários

---

## 📌 Exemplos de Uso Rápido

```bash
# grep — Buscar padrão
grep -i "flag" dump.txt

# awk — Mostrar primeira coluna
awk '{print $1}' arquivo.txt

# binwalk — Extrair dados ocultos
binwalk -e firmware.bin

# exiftool — Ver metadados
exiftool imagem.jpg

# file — Identificar tipo de arquivo
file arquivo

# find — Buscar arquivos por nome
find . -name "*.txt"

# grep — Buscar string em todos os arquivos
grep -r "flag" .

# hexdump — Visualizar bytes e ASCII
hexdump -C arquivo.bin

# sort — Ordenar linhas
sort palavras.txt

# strings — Extrair texto de binário
strings dump.bin

# uniq — Remover linhas duplicadas
sort arquivo.txt | uniq

# wc — Contar linhas
wc -l arquivo.txt

# xxd — Mostrar hexdump com ASCII
xxd -C arquivo.bin
```