# TRABALHO

# Atividades 21 a 25 — Git & GitHub

Este repositório contém a execução e o registro das atividades práticas 21 a 25.

## Atividade 21 — Configuração Inicial e Primeiro Fluxo Local

### Comandos utilizados
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"

git init
git status
git add todo.txt
git commit -m "feat: adiciona lista inicial de tarefas"
```

### Arquivo criado
`todo.txt` com três tarefas diárias.

---

## Atividade 22 — Autenticação Segura SSH e Conexão Remota

### Gerar a chave SSH
```bash
ssh-keygen -t ed25519 -C "seu-email@exemplo.com"
```

### Iniciar o SSH Agent
```bash
eval "$(ssh-agent -s)"
```

### Adicionar a chave privada
```bash
ssh-add ~/.ssh/id_ed25519
```

### Copiar a chave pública no Windows
```bash
clip < ~/.ssh/id_ed25519.pub
```

No GitHub: **Settings → SSH and GPG keys → New SSH key**.

### Testar a conexão
```bash
ssh -T git@github.com
```

---

## Atividade 23 — Isolamento de Recursos com Branches

### Criar e acessar a branch
```bash
git checkout -b feature-contatos
```

Na branch foi criado o arquivo `contato.html`.

### Adicionar e commitar
```bash
git add contato.html
git commit -m "feat: adiciona formulário de contato"
```

### Voltar para a main
```bash
git checkout main
```

### Mesclar
```bash
git merge feature-contatos
```

---

## Atividade 24 — Simulação de Conflito de Merge

Na `main`, a primeira linha de `todo.txt` é alterada para:

```text
Revisar Git à tarde
```

Na branch `teste-conflito`, a mesma linha é alterada para:

```text
Estudar Git de noite
```

Ao tentar:

```bash
git merge teste-conflito
```

o Git pode gerar:

```text
<<<<<<< HEAD
Revisar Git à tarde
=======
Estudar Git de noite
>>>>>>> teste-conflito
```

### Resolução
Escolher a versão correta, remover as marcações e executar:

```bash
git add todo.txt
git commit -m "fix: resolve conflito de merge"
```

---

## Atividade 25 — Sincronização e Colaboração via Fork

1. Clicar em **Fork** no repositório original no GitHub.
2. Clonar o fork:

```bash
git clone URL_DO_SEU_FORK
```

3. Adicionar o repositório original como `upstream`:

```bash
git remote add upstream URL_DO_REPOSITORIO_ORIGINAL
```

4. Fazer alterações, commit e push:

```bash
git add .
git commit -m "feat: realiza alteração no projeto"
git push origin main
```

5. No GitHub, clicar em **Compare & pull request** e depois em **Create pull request**.

6. Para atualizar o projeto local com o original:

```bash
git pull upstream main
```
