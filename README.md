# Site do Farol

Duas páginas estáticas, sem build e sem dependência: a **política de privacidade** (exigida
pelo Google Play no cadastro do app) e uma **página inicial** que serve como o campo
"Website" da ficha da loja.

```
index.html                    página inicial
politica-de-privacidade.html  política — o link obrigatório do Play Console
```

## Antes de publicar: preencher o e-mail

Os dois arquivos têm `SEU-EMAIL-AQUI` no lugar do contato. O Google **exige** um e-mail de
privacidade que funcione. Troque nos dois:

```bash
# Linux/macOS
sed -i 's/SEU-EMAIL-AQUI/seu@email.com/g' index.html politica-de-privacidade.html
```

No Windows, abra os dois arquivos e substitua `SEU-EMAIL-AQUI` pelo seu e-mail.

## Publicar no GitHub Pages (grátis)

1. Crie um repositório no GitHub chamado **`farol-site`** — pode ser público (o conteúdo é
   público de qualquer forma; a política PRECISA ser acessível sem login).
2. No terminal, dentro desta pasta:

   ```bash
   git remote add origin https://github.com/SEU-USUARIO/farol-site.git
   git branch -M main
   git push -u origin main
   ```

3. No GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)`**
   → Save.
4. Em um ou dois minutos as páginas ficam no ar:

   ```
   https://SEU-USUARIO.github.io/farol-site/
   https://SEU-USUARIO.github.io/farol-site/politica-de-privacidade.html
   ```

5. **Abra o segundo link numa janela anônima** antes de cadastrar no Play Console. Se ele não
   abrir sem login, a revisão do Google reprova.

## Onde esses links entram no Play Console

| Campo | Link |
|---|---|
| Política de Privacidade (obrigatório) | `.../politica-de-privacidade.html` |
| Website (opcional, recomendado) | `.../farol-site/` |
| E-mail de contato (obrigatório) | o mesmo que você colocou nos arquivos |

## Ao mudar a política depois

A política diz que "a data no topo será atualizada e a nova versão ficará neste mesmo
endereço". Cumpra isso: edite o arquivo, **troque a data no topo** e envie de novo. Não crie
uma URL nova — o link cadastrado no Play precisa continuar valendo.
