# 📦 Guia: Hospedar no GitHub Pages + Gerar APK

Este guia te leva do zero ao APK instalável, tudo pelo navegador, sem instalar programas.

Você vai usar os 6 arquivos do ZIP **saiedi-equip-site.zip**:
- `index.html` (o app)
- `manifest.webmanifest` (define nome e ícones)
- `sw.js` (suporte offline)
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` (ícones)

⚠️ **Importante:** mantenha os nomes exatamente assim e todos na mesma pasta (raiz). Não renomeie.

---

## PARTE 1 — Criar conta no GitHub (se ainda não tem)

1. Acesse https://github.com e clique em **Sign up**.
2. Crie com seu e-mail, escolha um nome de usuário (ex: `andre-saiedi`) e senha.
3. Confirme o e-mail.

---

## PARTE 2 — Criar o repositório e subir os arquivos

1. Logado no GitHub, clique no **+** no canto superior direito → **New repository**.
2. Em **Repository name**, digite: `saiedi-equip`
3. Marque a opção **Public** (precisa ser público para o GitHub Pages gratuito funcionar).
4. Clique em **Create repository**.

5. Na página que abrir, clique no link **"uploading an existing file"**
   (ou vá em **Add file** → **Upload files**).

6. **Descompacte o ZIP** `saiedi-equip-site.zip` no seu computador primeiro.
   Depois, **arraste os 6 arquivos** (não a pasta, os arquivos soltos) para a área de upload.

7. Espere os arquivos subirem e clique em **Commit changes** (botão verde embaixo).

---

## PARTE 3 — Ativar o GitHub Pages

1. No repositório, clique na aba **Settings** (engrenagem, no topo).
2. No menu da esquerda, clique em **Pages**.
3. Em **Source**, selecione **Deploy from a branch**.
4. Em **Branch**, escolha **main** e a pasta **/ (root)**.
5. Clique em **Save**.

6. Aguarde 1-2 minutos. Recarregue a página. No topo vai aparecer:
   > "Your site is live at **https://SEU-USUARIO.github.io/saiedi-equip/**"

7. **Copie esse link.** Abra ele no navegador para confirmar que o app carrega.
   ✅ Se o app abrir, está hospedado!

---

## PARTE 4 — Gerar o APK no PWABuilder

1. Acesse https://www.pwabuilder.com
2. Cole o link do seu app (ex: `https://seu-usuario.github.io/saiedi-equip/`) no campo central.
3. Clique em **Start** (ou na seta).

4. O PWABuilder analisa o app. Você verá uma pontuação do Manifest, Service Worker, etc.
   Como já preparei tudo, deve passar verde. Clique em **Package for stores** (no topo direito).

5. Escolha o card **Android**.
6. Clique em **Generate Package**.
   - Pode deixar as opções padrão.
   - O **Package ID** pode deixar como sugerido (ex: `com.saiedi.equip`).
7. Clique em **Download**.

8. Você recebe um ZIP. Dentro dele há o arquivo **`.apk`** (e também um `.aab`, que é para publicar na Play Store — pode ignorar por enquanto).
   - Use o arquivo terminado em **`-signed.apk`** se houver, ou o `.apk` disponível.

---

## PARTE 5 — Instalar o APK no celular

1. Envie o arquivo `.apk` para o celular (WhatsApp para você mesmo, e-mail, cabo ou OneDrive).
2. No celular, toque no arquivo `.apk`.
3. O Android vai avisar sobre "instalar de fontes desconhecidas":
   - Toque em **Configurações** → ative **Permitir desta fonte**.
4. Volte e toque em **Instalar**.
5. Pronto! O app **SAIEDI Equip** aparece na sua gaveta de apps com o ícone da lâmpada. 🎉

---

## 🔄 Como atualizar o app no futuro

Se eu te mandar uma versão nova do `index.html`:
1. No GitHub, entre no repositório → clique no `index.html` → ícone de lápis (Edit) → ou use **Add file → Upload files** para substituir.
2. Commit.
3. O GitHub Pages atualiza sozinho em ~1 min.
4. Gere o APK de novo no PWABuilder (ou, como o app usa service worker, ele se atualiza sozinho ao abrir com internet).

---

## ❓ Problemas comuns

**"O app não abre no link do GitHub Pages"**
→ Espere mais 2 minutos (a primeira publicação demora). Confirme que o arquivo se chama exatamente `index.html`.

**"PWABuilder reclama do Service Worker ou Manifest"**
→ Confirme que os 6 arquivos estão na raiz do repositório (não dentro de uma subpasta). O link deve terminar com `/saiedi-equip/`.

**"O APK não instala no celular"**
→ Ative "Instalar apps desconhecidos" para o app pelo qual você abriu o APK (Arquivos, Chrome ou WhatsApp).

**"A câmera não abre no APK"**
→ Na primeira vez, o Android pede permissão de câmera. Aceite. Se negou sem querer: Configurações → Apps → SAIEDI Equip → Permissões → Câmera → Permitir.

---

## 💡 Alternativa mais simples (sem APK)

Se em algum momento o APK der trabalho, lembre que com o link do GitHub Pages você também pode só abrir no Chrome do celular e usar **"Instalar app" / "Adicionar à tela inicial"** — fica praticamente igual a um APK, com o mesmo ícone e tela cheia, e atualiza sozinho. O APK só vale a pena se você quiser distribuir o arquivo para outras pessoas da equipe.
