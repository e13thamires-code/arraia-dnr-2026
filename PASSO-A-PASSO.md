# 🎉 Colocar o Arraiá DNR 2026 no ar (projeto casa-tha)

✅ O config do Firebase já está encaixado (projeto **casa-tha**).
✅ Os dados do arraiá ficam isolados numa "gaveta" só dele (coleção `arraia2026`) —
o resto do casa-tha **não é tocado**.

Faltam só **2 etapas**: adicionar as regras e publicar o site.

---

## ✅ Etapa A — Adicionar as regras do banco (no navegador)

🔗 **https://console.firebase.google.com/project/casa-tha/firestore/rules**

- Abra o arquivo **`REGRAS-PARA-ADICIONAR.txt`** (está nesta mesma pasta).
- Cole o bloco indicado **junto** com as suas regras atuais (sem apagar nada).
- Clique em **Publicar**.

> Isso libera **só** a gaveta `arraia2026`. Tudo o mais no casa-tha continua protegido.

---

## ✅ Etapa B — Publicar o site (no PowerShell)

Abra o PowerShell **dentro da pasta `arraia-dnr-site`** e rode, na ordem:

```powershell
# 1) Instala a ferramenta do Firebase (só na 1ª vez)
npm install -g firebase-tools

# 2) Login na sua conta Google (abre o navegador)
firebase login

# 3) Cria um endereço SEPARADO pro arraiá (não mexe num site que o casa-tha já tenha)
firebase hosting:sites:create arraia-dnr-2026

# 4) Publica SÓ o site (não toca nas regras do banco)
firebase deploy --only hosting
```

No fim aparece:

```
Hosting URL: https://arraia-dnr-2026.web.app
```

🎊 **Esse é o link do site!** Manda no grupo do WhatsApp.

> Se o nome `arraia-dnr-2026` já estiver em uso (é um nome global), troque por outro
> no comando do passo 3 **e** no arquivo `firebase.json` (campo `"site"`), ex: `arraia-dnr-thamires`.

---

## 🔁 Mudar algo depois
Edite `public/index.html` e rode de novo:
```powershell
firebase deploy --only hosting
```

## 🔧 Opcionais (dá pra trocar no public/index.html)
- **Grupo do WhatsApp:** troque `https://chat.whatsapp.com/SEU-LINK-DO-GRUPO`.
- **Playlist do Spotify:** troque `https://open.spotify.com/` pelo link real.
- **Pix:** confira o "copia e cola" no app do banco antes de divulgar.

## 🔒 Segurança
As regras liberam leitura/escrita **só** na coleção `arraia2026` e **travam sozinhas
em 31/08/2026**. O restante do projeto casa-tha segue com as suas regras de sempre.
```
