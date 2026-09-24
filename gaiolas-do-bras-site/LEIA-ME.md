# Gaiolas do Brás — site + painel de edição

Este pacote tem tudo pronto: o site (`index.html` + `assets/`), os dados
editáveis (`data/`) e o painel de login (`admin/`).

## Estrutura
- `index.html` — o site
- `assets/` — imagens (logo, passeador, gaiola, rifa)
- `data/config.json` — WhatsApp, preço, dezena da rifa, link do grupo, ID do Google Analytics
- `data/reviews.json` — as avaliações dos clientes (com vídeo)
- `admin/` — o painel de edição (Decap CMS)

## Publicar no Netlify (com login pro dono editar)

O login só funciona quando o site está num repositório Git (GitHub) conectado ao Netlify.

1. **Suba esta pasta pro GitHub** (crie um repositório novo e envie os arquivos).
2. No **Netlify**: *Add new site → Import from Git* → escolha o repositório.
   - Build command: deixe vazio. Publish directory: `/` (raiz).
3. **Ative o login**: no painel do site → *Identity* → **Enable Identity**.
4. Em *Identity → Registration*, marque **Invite only** (só quem você convidar entra).
5. Em *Identity → Services*, clique em **Enable Git Gateway**.
6. Em *Identity → Invite users*, convide o **e-mail do dono**. Ele recebe um e-mail,
   cria a senha e pronto.
7. O dono acessa **seusite.com/admin** → faz login → edita textos, preço, dezena,
   link do grupo e **avaliações (com vídeo)**. Ao salvar, publica sozinho.

> Só arrastar a pasta no Netlify (sem GitHub) também publica o site, mas o
> **/admin não terá login** — pra isso precisa do passo com GitHub + Identity acima.

## Google Analytics (cliques nos botões)
Em `data/config.json` (ou no painel, em *Configurações*), coloque seu **ID do GA4**
no campo `ga_id` (formato `G-XXXXXXXXXX`). Os cliques aparecem no GA4 em
*Relatórios → Eventos → `clique_botao`*.

## Avaliações com vídeo
No painel, em **Avaliações dos clientes**, é só adicionar:
- Nome, cidade, nota (estrelas), depoimento
- Cole o **link do vídeo do YouTube** (o cliente manda no WhatsApp, você sobe no
  YouTube e cola aqui) — ou o **link do Instagram**.

O vídeo aparece direto na seção "Avaliações" do site.
