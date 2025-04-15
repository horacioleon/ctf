# 🔐 Encodes e Hashes Comuns em Hacking e Pentest

Este documento lista os encodes e hashes mais usados por hackers, CTF players e pentesters, junto com exemplos e ferramentas Linux para decodificá-los.

---

## 📦 Tabela de Encodes & Hashes

| Tipo         | Exemplo                                                  | Finalidade Comum                                      | Ferramenta CLI para Decodificar                     |
|--------------|----------------------------------------------------------|-------------------------------------------------------|-----------------------------------------------------|
| **Base64**   | `cGFzc3dvcmQ6MTIzNA==`                                   | Exfiltração de dados, payloads HTTP                   | `base64 -d`, `echo ... | base64 -d`               |
| **URL Encode** | `..%2F..%2Fetc%2Fpasswd`                              | LFI, XSS, SQLi, bypasses                              | `urldecode`, `python -c` script, `cyberchef`        |
| **Hex (Base16)** | `414243`                                            | Obfuscation, shellcode                               | `xxd -r -p`, `echo ... | xxd -r -p`               |
| **MD5**      | `5f4dcc3b5aa765d61d8327deb882cf99` (hash de "password") | Senhas antigas, rainbow tables                       | `hashcat`, `john`, `crackstation.net`               |
| **SHA-1**    | `5baa61e4c9b93f3f0682250b6cf8331b7ee68fd8`              | Hash legado                                           | `hashcat`, `john`, `sha1sum`                        |
| **SHA-256**  | `9f86d081...`                                           | Verificação de arquivos, senhas modernas             | `sha256sum`, `hashid`                               |
| **Base32**   | `JBSWY3DPEBLW64TMMQ======`                              | 2FA (TOTP), stealth                                  | `base32 -d`, `python -m base64`                     |
| **ROT13**    | `uryyb`                                                 | Obfuscation leve, easter eggs                        | `tr 'A-Za-z' 'N-ZA-Mn-za-m'`, `codecs.encode`       |
| **JWT**      | `eyJhbGciOi...`                                         | Tokens de autenticação                               | `jwt-tool`, `python -m jwt`, `cyberchef`            |
| **HTML Entities** | `&lt;script&gt;`                                  | XSS, bypass                                          | `html-entities`, `python html.unescape()`           |
| **Ascii85**  | `9jqo^BlbD-BleB1DJ+*+F(f,q`                             | Payloads binários em exploits                        | `python -m base64`, `perl`, `cyberchef`             |
| **Base58**   | `StV1DL6CwTryKyV`                                       | Bitcoin, stealth                                     | `base58`, `python-base58`, `CyberChef`              |

---

## 🛠 Ferramentas Recomendadas

### CLI

- `base64`, `base32`, `xxd`, `tr`, `cut`, `jq`
- `hashid` – detecta tipo de hash
- `hashcat` – cracking de hashes
- `john` – cracking com wordlists
- `jwt-cli` – inspeção de JWTs
- `urldecode` (via `perl -MURI::Escape` ou `python`)
- `openssl` – suporte a diversos encodes e hashes

### Python (exemplos rápidos)
```bash
# Base64
python3 -c 'import base64; print(base64.b64decode("cGFzc3dvcmQ6MTIzNA==").decode())'

# URL decode
python3 -c 'import urllib.parse; print(urllib.parse.unquote("..%2Fetc%2Fpasswd"))'

# ROT13
python3 -c 'import codecs; print(codecs.encode("uryyb", "rot_13"))'

# JWT decode (header)
python3 -c 'import base64, json; print(json.loads(base64.urlsafe_b64decode("eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"+"==")))'
