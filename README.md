# sucodejoyce — Portfolio

Portfólio pessoal de Joyce Soares, Designer especializada em social media, branding e conteúdo digital.

**Live:** [sucodejoyce.cargo.site](https://sucodejoyce.cargo.site) *(versão anterior)*  
**Nova versão:** Este repositório

---

## 🗂 Estrutura do Projeto

```
sucodejoyce/
├── index.html              ← Homepage com todos os projetos
├── css/
│   └── style.css           ← Todos os estilos
├── js/
│   └── main.js             ← Cursor, animações, menu mobile, form
├── pages/
│   ├── about.html          ← CV, skills, experiência, mídia
│   └── contact.html        ← Formulário de contato
└── assets/
    └── img/                ← Coloque suas imagens aqui
```

---

## 🚀 Como subir no GitHub Pages

### 1. Criar repositório no GitHub

```bash
git init
git add .
git commit -m "feat: initial portfolio"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/sucodejoyce.git
git push -u origin main
```

### 2. Ativar GitHub Pages

- Acesse o repositório no GitHub
- Vá em **Settings → Pages**
- Em "Source", selecione **Deploy from a branch**
- Escolha `main` / `root`
- Clique em **Save**

Seu site estará disponível em:  
`https://SEU_USUARIO.github.io/sucodejoyce/`

### 3. Domínio personalizado (opcional)

Para usar `sucodejoyce.com.br` ou similar:
- Crie um arquivo chamado `CNAME` na raiz com o conteúdo:
  ```
  www.sucodejoyce.com.br
  ```
- Configure o DNS do seu domínio com um CNAME apontando para `SEU_USUARIO.github.io`

---

## 🖼 Adicionando suas imagens

Substitua os placeholders coloridos pelas imagens reais dos seus projetos.

Em cada `<article class="project">` no `index.html`, substitua o bloco `.project-img--placeholder` por:

```html
<div class="project-img">
  <img src="../assets/img/nome-do-projeto.jpg" alt="Descrição do projeto" loading="lazy" />
</div>
```

**Dica:** Use imagens com proporção 4:3 (ex: 800×600px) para os cards normais.

---

## 📬 Ativando o formulário de contato

O formulário atualmente apenas simula o envio. Para torná-lo funcional, use um dos serviços abaixo:

### Opção A — Formspree (gratuito, sem backend)

1. Crie conta em [formspree.io](https://formspree.io)
2. Crie um novo form e copie o endpoint
3. No `contact.html`, troque:
   ```html
   <form class="contact-form" id="contact-form" novalidate>
   ```
   por:
   ```html
   <form class="contact-form" id="contact-form" action="https://formspree.io/f/SEU_ID" method="POST">
   ```
4. Remova o `e.preventDefault()` do `main.js` (ou mantenha e use fetch)

### Opção B — EmailJS (envio direto do browser)

1. Crie conta em [emailjs.com](https://www.emailjs.com)
2. Configure seu serviço de email e template
3. Adicione o SDK no `<head>`:
   ```html
   <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
   ```
4. No `main.js`, substitua o `setTimeout` por:
   ```js
   emailjs.sendForm('SERVICE_ID', 'TEMPLATE_ID', form, 'PUBLIC_KEY')
     .then(() => { btn.textContent = 'Enviado ✓'; })
     .catch(() => { btn.textContent = 'Erro. Tente novamente.'; });
   ```

---

## ✏️ Personalizações rápidas

| O que mudar | Onde |
|---|---|
| Cores principais | `css/style.css` → variáveis `:root` |
| Foto de perfil | `pages/about.html` → `.about-img-placeholder` |
| Projetos e descrições | `index.html` → cada `<article class="project">` |
| Skills e percentuais | `pages/about.html` → `.skill-fill` (atributo `width`) |
| Links de projetos | `index.html` → `.project-link` (atributo `href`) |
| Email de contato | Todos os arquivos → `joyce.soaresg2@gmail.com` |

---

## 🎨 Decisões de design

- **Tipografia:** Playfair Display (display/títulos) + DM Sans (corpo/UI)
- **Paleta:** Off-white quente `#f5f2ec` + preto suave `#0e0d0c` + terracota `#d4522a`
- **Animações:** Reveal suave via IntersectionObserver + cursor customizado
- **Layout:** Grid assimétrico, tipografia grande, espaço negativo generoso

---

## 📄 Licença

© 2025 Joyce Soares. Todos os direitos reservados.
