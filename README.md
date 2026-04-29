# ☁️ Busca CEP Cloud (PWA)

Fala pessoal! Esse aqui é o **Busca CEP Cloud**, um projeto que desenvolvi para facilitar a vida de quem precisa consultar CEPs e endereços pelo Brasil. A ideia central foi pegar uma aplicação web tradicional e dar uma cara de "aplicativo de celular" usando conceitos de **Progressive Web App (PWA)**.

## 🎯 Qual é a desse projeto?
Sabe quando você precisa preencher um cadastro e não lembra o CEP? O objetivo aqui é resolver isso de forma bem rápida e direta. 
Para deixar o projeto mais robusto, eu apliquei conceitos de PWA, o que significa que o site pode ser instalado no celular e até mesmo abrir quando a internet cai ou fica instável.

**O que eu usei debaixo dos panos:**
- HTML5, CSS3 e JavaScript puro (ES6+)
- **Materialize CSS** pra deixar o visual responsivo e bonitão sem sofrer muito.
- **Fetch API & Axios** pra fazer as requisições nas APIs do ViaCEP e do IBGE.
- **Service Workers & Web App Manifest** pra fazer a mágica do PWA acontecer.

---

## 📱 Mas afinal, o que é um PWA?
Basicamente, um **PWA (Progressive Web App)** é um site que tomou anabolizantes rs. Ele usa tecnologias modernas nos navegadores pra se comportar igualzinho a um aplicativo nativo (tipo os que a gente baixa na Play Store).

Aqui no projeto, apliquei as seguintes características:

- **Dá pra instalar:** Graças ao `manifest.json`, o navegador entende que esse site é um app. Você pode adicionar à tela inicial do celular ou do PC e ele abre numa janela própria, sem aquela barra de pesquisa chata do Chrome.
- **Funciona offline (ou quase isso):** É aqui que entra o `service-worker.js`. Ele fica no meio do caminho entre o navegador e a internet. Quando você acessa o site pela primeira vez, ele salva (cacheia) a estrutura toda (HTML, CSS, botões, ícones). Se você ficar sem internet e abrir o app, a tela vai carregar normalmente, sem aquele dinossauro do Google. (Só a busca do CEP em si que vai avisar que você está sem rede, claro).
- **Responsivo:** Funciona liso no celular, tablet ou monitor ultrawide.

---

## 🚀 Como testar o projeto no seu PC

Como o projeto usa Service Workers, você não pode simplesmente dar dois cliques no `index.html`. O navegador bloqueia isso por segurança. Você precisa de um servidorzinho local.

**Jeito mais fácil (pelo VS Code):**
1. Instale a extensão **Live Server**.
2. Clique com o botão direito no `index.html` e vai em "Open with Live Server".
3. Pronto, ele abre sozinho no seu navegador.

**Pelo terminal (pra quem curte Node.js):**
Se tiver o Node instalado, abre o terminal na pasta do projeto e roda:
```bash
npx serve .
```
Aí é só acessar o `http://localhost:3000` (ou o link que ele gerar) no seu navegador.

---

## 🌐 Como eu fiz o deploy no Netlify

Pra colocar isso no ar de graça e bem rápido, escolhi o Netlify. Se você for fazer igual, tem dois caminhos:

### 1. O jeito "arrasta e solta" (Netlify Drop)
1. Pega a pasta inteira do projeto (com o `index.html` e tudo mais).
2. Entra no [app.netlify.com/drop](https://app.netlify.com/drop).
3. Literalmente arrasta a pasta pra dentro da tela.
4. Em 5 segundos o site tá no ar. Depois você pode ir nas configurações e trocar o link pra algo mais bonito.

### 2. O jeito profissional (Linkando com o GitHub)
Foi o que eu fiz pra ficar mais organizado:
1. Subi todo esse código pro meu GitHub.
2. Fui no painel do Netlify e cliquei em **Add new site** > **Import an existing project**.
3. Loguei com o GitHub e selecionei esse repositório (`busca-cep-cloud`).
4. Como é só HTML/JS (não tem build de React ou coisa assim), deixei as configurações em branco e cliquei em **Deploy**.
5. E a mágica acontece. Qualquer alteração que eu faço no GitHub (quando dou um push), o Netlify já atualiza o site sozinho.

**🚀 Olha como ficou:**
Acesse aqui a versão final rodando lisinha: 
`[Insira o link final do Netlify aqui, ex: https://busca-cep-cloud.netlify.app]`
