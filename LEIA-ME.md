# Treino Ivan — Instalação no iPhone

## O que é isso?

Um PWA (Progressive Web App) do seu treino. Depois de instalado no iPhone, funciona **igual a um app nativo**: ícone na tela inicial, abre em tela cheia, sem barra do Safari, com timer, checkboxes de progresso e vibração/som ao fim do descanso.

---

## Passo 1 — Suba pro GitHub (5 minutos)

### 1.1. Crie uma conta no GitHub
- Acesse https://github.com/signup (se ainda não tem)
- Grátis, leva 1 minuto

### 1.2. Crie um repositório
- Clique em **"New repository"** (ou https://github.com/new)
- **Repository name:** `treino` (ou o nome que quiser)
- Marque **Public** (precisa ser público para o GitHub Pages funcionar grátis)
- Marque **Add a README file**
- Clique **Create repository**

### 1.3. Faça upload dos 5 arquivos
- Dentro do repositório, clique em **Add file → Upload files**
- Arraste os 5 arquivos desta pasta:
  - `index.html`
  - `manifest.json`
  - `sw.js`
  - `icon-192.png`
  - `icon-512.png`
- Clique **Commit changes**

### 1.4. Ative o GitHub Pages
- No repositório, vá em **Settings** (aba no topo)
- No menu lateral, clique em **Pages**
- Em **"Source"**, selecione **Deploy from a branch**
- Em **"Branch"**, selecione `main` e `/ (root)`
- Clique **Save**
- Aguarde 1–2 minutos

### 1.5. Copie seu link
Depois de ativado, o GitHub mostra o link no topo da página Pages, algo como:
```
https://SEU_USUARIO.github.io/treino/
```

---

## Passo 2 — Instale no iPhone

1. Abra o **Safari** no iPhone (não funciona no Chrome pra isso no iOS)
2. Cole o link `https://SEU_USUARIO.github.io/treino/`
3. Espere carregar (só uma vez — depois fica offline)
4. Toque no botão de **Compartilhar** (quadrado com seta pra cima, no rodapé)
5. Role e toque em **"Adicionar à Tela de Início"**
6. Confirme o nome (pode deixar "Treino Ivan")
7. Toque em **Adicionar**

Pronto. Na Tela de Início agora tem um ícone preto com "TI" que abre em tela cheia, **sem barra de Safari, sem cara de site**.

---

## Como usar o app

- **Aba "VISÃO"** — perfil, índice das 5 rotinas e princípios
- **Abas A / B / C / D / E** — cada rotina com progresso visual
- **Toque em qualquer exercício** pra marcar como feito (checkbox verde, vibração leve)
- **Timer de descanso** (rodapé) — toque em 60s/90s/2m/3m e ▶ para iniciar. Toca um beep + vibra quando zera
- **"Resetar dia"** no fim de cada rotina limpa os checkboxes

---

## Funciona offline?

**Sim**, depois da primeira abertura. O service worker cacheia todos os arquivos. Pode fechar o app, ficar sem internet na academia, e continua funcionando normalmente.

**Limitação consciente:** o estado dos checkboxes e do timer reseta quando você fecha totalmente o app. Isso é por escolha (você pediu sem localStorage). Se quiser que persista entre sessões, me avise que eu ajusto.

---

## Manutenção

Se quiser mudar alguma coisa no treino (adicionar exercício, trocar reps, etc.):
1. No GitHub, edite o arquivo `index.html` direto pelo navegador
2. Commit
3. Em 1 minuto a mudança sobe e na próxima vez que abrir o app no iPhone ele atualiza sozinho (pode precisar fechar e reabrir 2 vezes pro service worker pegar a nova versão)
