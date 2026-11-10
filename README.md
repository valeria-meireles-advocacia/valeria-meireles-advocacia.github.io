# Valéria Meireles Advocacia — Site institucional

Site estático (HTML + CSS + JavaScript puro), sem banco de dados e sem bibliotecas externas.
Feito para publicar gratuitamente no **GitHub Pages** com domínio próprio do **Registro.br**.

```
├── index.html          → página principal
├── privacidade.html    → Política de Privacidade (LGPD)
├── 404.html            → página de "não encontrado"
├── css/style.css       → visual (cores e fontes no topo do arquivo)
├── js/main.js          → animações, menu, formulário → WhatsApp
├── assets/img/         → logotipo, ícone e imagem de compartilhamento
├── favicon.png
├── CNAME               → seu domínio (GitHub Pages lê este arquivo)
├── robots.txt / sitemap.xml → para o Google
└── .nojekyll           → GitHub publica os arquivos como estão
```

---

## 1. O que você precisa editar

Procure por **`EDITAR`** nos arquivos (Ctrl+F). Os principais:

| O quê | Onde |
|---|---|
| Número da OAB | `index.html` (seção Sobre e rodapé), `privacidade.html`, `404.html` |
| Telefone / WhatsApp | `index.html` (contato, botão flutuante, dados estruturados) e `js/main.js` (`const WHATSAPP`) |
| Horário de atendimento | `index.html` (contato) |
| Domínio | `CNAME`, `robots.txt`, `sitemap.xml` e as tags `canonical` / `og:` no topo dos HTML |
| Foto profissional | troque a imagem da seção “O escritório” (`assets/img/`) |
| Textos | direto no `index.html` |

> Dica: o número de WhatsApp vai **só com dígitos**, com 55 + DDD. Ex.: `5583912345678`.

---

## 2. Publicar no GitHub Pages

1. Crie uma conta em <https://github.com> e clique em **New repository**.
2. Nome sugerido: `site-valeria-meireles`. Marque **Public** (no plano gratuito, o Pages exige repositório público — isso não é problema, porque não há nada secreto no site).
3. Clique em **uploading an existing file** e arraste **todo o conteúdo** desta pasta (não a pasta em si). Clique em **Commit changes**.
4. Vá em **Settings → Pages**:
   - *Source*: **Deploy from a branch**
   - *Branch*: **main** / pasta **/(root)** → **Save**
5. Em 1–2 minutos o site aparece em `https://SEU-USUARIO.github.io/site-valeria-meireles/`.

## 3. Ligar o domínio do Registro.br

1. Registre o domínio (sugestão para advogados: **`.adv.br`**, que exige inscrição na OAB — ex.: `valeriameireles.adv.br`).
2. No painel do Registro.br, abra o domínio → **DNS** → **Configurar zona DNS** e crie:

   | Tipo | Nome | Valor |
   |---|---|---|
   | A | *(vazio / @)* | `185.199.108.153` |
   | A | *(vazio / @)* | `185.199.109.153` |
   | A | *(vazio / @)* | `185.199.110.153` |
   | A | *(vazio / @)* | `185.199.111.153` |
   | CNAME | `www` | `SEU-USUARIO.github.io` |

3. No GitHub: **Settings → Pages → Custom domain** → digite `www.seudominio.adv.br` → **Save**.
4. Quando o DNS propagar (de minutos a algumas horas), marque **Enforce HTTPS** (cadeado gratuito).

## 4. Colocar no Google

1. Acesse o **Google Search Console** (<https://search.google.com/search-console>) e adicione o domínio.
2. Confirme a propriedade com o registro TXT que o Google mostrar (criado no DNS do Registro.br).
3. Em **Sitemaps**, envie `sitemap.xml`.
4. Recomendado: crie/atualize o **Perfil da Empresa no Google** (Google Meu Negócio) com o mesmo endereço e telefone e coloque o link do site — é o que mais ajuda em buscas locais como “advogada previdenciária Sapé”.

---

## 5. Segurança — o que foi feito

- **Site estático**: não há servidor, login, banco de dados nem painel administrativo para ser invadido.
- **Zero bibliotecas de terceiros** (sem jQuery, sem plugins): nada de código alheio rodando no site.
- **Content-Security-Policy** no `<head>`: o navegador só executa scripts do próprio site — mesmo que alguém tente injetar código, ele é bloqueado.
- **O formulário não guarda nada**: ele só monta a mensagem e abre o WhatsApp no aparelho do visitante.
- Links externos com `rel="noopener noreferrer"`.
- **HTTPS** obrigatório pelo GitHub Pages.

**Cuidados daqui pra frente**

- Ative a **verificação em duas etapas** na conta do GitHub e no Registro.br — o maior risco real é alguém roubar sua conta, não o código.
- Nunca coloque senhas, tokens ou arquivos `.env` no repositório (o `.gitignore` já ajuda).
- Se um dia adicionar scripts de fora (Google Analytics, chat, Pixel), inclua o domínio deles no `Content-Security-Policy` e avise isso na Política de Privacidade.

---

## 6. Conformidade com a OAB (Provimento 205/2021 e Código de Ética)

O conteúdo foi escrito em tom **informativo e sóbrio**. Antes de publicar, confira:

- [x] Nome da advogada e **número da OAB** visíveis
- [x] Sem promessa de resultado, sem “garantia”, sem “ganhe sua causa”
- [x] Sem preços, sem “consulta grátis”, sem promoções
- [x] Sem depoimentos de clientes, números de processos ganhos ou valores obtidos
- [x] Sem expressões de autoengrandecimento (“o melhor”, “nº 1”)
- [x] Aviso de caráter informativo no rodapé
- [ ] Revisar os textos finais com o seu olhar de advogada antes de publicar

---

## 7. Usar como modelo para outros escritórios

1. No GitHub, abra o repositório → **Settings** → marque **Template repository**.
2. Para cada cliente: **Use this template** → novo repositório → troque logo (`assets/img/`), cores (topo do `css/style.css`), textos e os itens marcados com `EDITAR`.
3. As cores principais estão em `:root` no `css/style.css` (`--cafe`, `--bronze`, `--ouro`...).
