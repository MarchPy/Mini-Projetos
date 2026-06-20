# 🛠️ Toolbox — Scripts e Ferramentas

![Python](https://img.shields.io/badge/Python-3.10%2B-yellow?style=flat-square&logo=python)
![Go](https://img.shields.io/badge/Go-1.20%2B-00ADD8?style=flat-square&logo=go)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

Coleção de pequenas ferramentas e scripts desenvolvidos para fins de estudo e prática: criptografia, hashing, geração de senhas e automação de tarefas simples do dia a dia.

Cada pasta é um projeto independente, com seu próprio código e dependências.

## 📂 Projetos

| Projeto                                    | Linguagem | Descrição                                 |
| ------------------------------------------ | --------- | ------------------------------------------- |
| [`editor-de-texto/`](#-editor-de-texto)     | Python    | Editor de texto leve e portátil            |
| [`gerador-de-senhas/`](#-gerador-de-senhas) | Python    | Gerador de senhas com interface gráfica    |
| [`xencryptpy/`](#-xencryptpy)               | Python    | Criptografia simétrica de arquivos         |
| [`hash-checker/`](#-hash-checker)           | Python    | Verificador de hashes MD5 / SHA256 / SHA512 |
| [`brutehash/`](#-brutehash)                 | Go        | CLI para identificação e quebra de hashes |

## 📁 Estrutura do repositório

```
.
├── README.md
├── Editor-de-texto/
│   ├── Editor.exe
│   ├── README.md
│   └── src/
│       └── text_edit.py
├── Gerador-de-senhas-GUI/
│   ├── Gerador de senhas.exe
│   ├── README.md
│   ├── run.sh
│   └── src/
│       └── genpw.py
├── XEncryptPy/
│   ├── README.md
│   ├── requirements.txt
│   ├── XEncryptPy.py
│   ├── CoreProgram/
│   │   └── CoreProgram.py
│   ├── Frames/
│   │   ├── Application.py
│   │   ├── BottomFrame.py
│   │   └── TopFrame.py
│   └── Images/
│       └── icone.png
├── SHA-and-MD5-checker/
│   ├── Hash Checker.py
│   ├── README.md
│   ├── requirements.txt
│   └── images/
│       ├── files.ico
│       └── icone.png
└── BruteHash/
    ├── BruteHash.go
    ├── README.md
    ├── go.mod
    ├── go.sum
    └── Core/
        ├── classification.go
        ├── generator.go
        ├── identifier.go
        └── wordlist.go
```

> Mantive o `README.md` individual de cada projeto dentro da própria pasta (histórico/detalhes específicos). Se preferir, pode apagá-los e deixar só este README geral na raiz.

## ⚙️ Requisitos gerais

- **Python 3.10+** com Tkinter
  - Linux: `sudo apt install python3-tk`
- **Go 1.20+** (apenas para o BruteHash)

Dependências Python combinadas (crie um `requirements.txt` na raiz ou um por pasta):

```
cryptography
pandas
```

---

### 📝 Editor de Texto

Editor de texto simples e portátil — abra, escreva e salve arquivos em qualquer lugar (ex: a partir de um pendrive).

**Tecnologia:** Tkinter

**Como usar:**

- No linux:

```bash
  cd Editor-de-Texto
  $ python3 text_edit.py
```

---

### 🔑 Gerador de Senhas

Gera senhas de 4, 6, 8 e 12 dígitos, com opção de letras maiúsculas, minúsculas, números e caracteres especiais. Interface gráfica em Tkinter.

**Tecnologia:** Tkinter

**Como usar:**

```bash
cd gerador-de-senhas
python3 genpw.py 
```

---

### 🔐 XEncryptPy

Criptografa e descriptografa arquivos usando criptografia simétrica (Fernet, da biblioteca `cryptography`).

**Tecnologia:** Tkinter, cryptography

**Como usar:**

```bash
cd xencryptpy
pip install -r requirements.txt
python3 XEncryptPy.py
```

> ⚠️ Evite criptografar o mesmo arquivo mais de uma vez — pode causar inconsistências.

---

### 🔍 Hash Checker

Calcula os hashes MD5, SHA256 e SHA512 de qualquer arquivo selecionado pelo usuário.

**Tecnologia:** Tkinter, Pandas, Hashlib

**Como usar:**

```bash
cd SHA-and-MD5-checker
pip install -r requirements.txt
python3 "Hash Checker.py"
```

---

### 🧩 BruteHash

Ferramenta de linha de comando em Go para identificação e quebra de hashes (MD5, SHA-1, SHA-256, SHA-512), pensada para testes de penetração e auditoria de segurança. Inclui:

- **Bruteforce por wordlist** — testa uma lista de palavras contra um hash alvo
- **Bruteforce por força bruta** — gera combinações dentro de um intervalo de tamanho
- **Identifier** — identifica o tipo de hash a partir do seu comprimento

**Tecnologia:** Go, urfave/cli

**Como usar:**

```bash
cd BruteHash

# Quebra por wordlist
./BruteHash.go bruteforce1 -w wordlist.txt -t <hash> --type sha256

# Quebra por força bruta
./BruteHash.go bruteforce2 -t <hash> --type sha256 --min 5 --max 10

# Identificar tipo de hash
./BruteHash.go identifier -t <hash>
```

---

## 👤 Autor

**João Pedro Alexandre Marchiori** ([@MarchPy](https://github.com/MarchPy))
