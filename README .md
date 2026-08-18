# Como publicar o ELO PATH em elopath.eloquaingles.com.br, só para a Rebeca

Este pacote tem tudo pronto pra você subir no GitHub. O resultado é um link
dentro do seu próprio domínio (`elopath.eloquaingles.com.br`), que não
aparece em nenhum lugar do site principal e não é indexado pelo Google, mas
funciona pra qualquer pessoa que receber o link (inclusive a Rebeca).

Importante entender antes de começar: isso é **privacidade por obscuridade**,
não é login com senha. Ninguém vai encontrar o link navegando pelo seu site
ou pesquisando no Google, mas quem tiver o link consegue abrir. Pra maioria
dos casos de uso (mandar pra uma aluna) isso é suficiente e é exatamente o
que você pediu. Se um dia você quiser exigir login de verdade, tem uma opção
no fim deste arquivo.

## Passo 1 — Criar o repositório no GitHub

1. Entre em github.com e crie uma conta, se ainda não tiver.
2. Clique em **New repository**.
3. Dê um nome discreto, que não entregue "Rebeca" nem "Eloqua" no nome
   (por exemplo `elopath-jornada-04x9`). Isso ajuda a manter o link pouco
   óbvio.
4. Deixe como **Public** (o plano gratuito do GitHub Pages exige repositório
   público; o conteúdo fica tecnicamente acessível por quem tiver o link
   exato, mas não aparece em buscas nem em listagens).
5. Crie o repositório.

## Passo 2 — Subir os arquivos

1. Dentro do repositório, clique em **Add file → Upload files**.
2. Envie os quatro arquivos deste pacote: `index.html`, `robots.txt`, `CNAME`
   e este `README.md` (o README é só documentação, não afeta o site).
3. Clique em **Commit changes**.

## Passo 3 — Ativar o GitHub Pages

1. Vá em **Settings → Pages** (menu lateral do repositório).
2. Em **Source**, escolha **Deploy from a branch**.
3. Branch: `main`, pasta: `/ (root)`.
4. Salve. Em 1 ou 2 minutos o GitHub mostra o link, algo como:
   `https://seu-usuario.github.io/elopath-jornada-04x9/`

Esse link já funciona e já é privado no sentido que você pediu: ninguém acha
ele sem você mandar diretamente.

## Passo 4 — Colocar no seu próprio domínio (elopath.eloquaingles.com.br)

Este pacote já vem pronto pra isso: incluí um quarto arquivo, chamado
`CNAME` (sem extensão), com o endereço `elopath.eloquaingles.com.br` escrito
dentro. Suba ele junto com os outros três no Passo 2. Se quiser um nome
diferente de "elopath" (por exemplo "jornada" ou "rebeca"), é só abrir esse
arquivo e trocar o texto antes de subir, ou depois direto pelo GitHub.

1. No painel do registro.br, entre na área de **DNS** do domínio
   eloquaingles.com.br.
2. Crie um registro novo do tipo **CNAME**:
   - Nome/host: `elopath` (ou o nome que você escolheu no arquivo CNAME)
   - Valor/destino: `seu-usuario.github.io` (troque `seu-usuario` pelo seu
     usuário real do GitHub, sem a barra nem o nome do repositório depois)
   - TTL: pode deixar o padrão sugerido pelo registro.br
3. Volte no GitHub, em **Settings → Pages**, no campo **Custom domain**
   digite `elopath.eloquaingles.com.br` e salve. O GitHub confirma sozinho
   que o CNAME está certo (pode levar alguns minutos).
4. Marque a opção **Enforce HTTPS**, se ela aparecer marcável (às vezes só
   fica disponível depois que o domínio é validado, então pode voltar aqui
   em algumas horas pra ativar).
5. Espere a propagação do DNS. Geralmente funciona em minutos, mas pode
   levar até algumas horas dependendo do registro.br.

Esse CNAME é um registro novo e separado dos que você já tem. Não mexe nos
registros MX do Google Workspace nem em nada do seu site principal, então
não tem risco pro seu e-mail nem pro resto do eloquaingles.com.br.

O link final que você vai mandar pra Rebeca fica:
**https://elopath.eloquaingles.com.br**

## Passo 5 — Mandar o link só pra Rebeca

Envie o link (o do GitHub Pages ou o do subdomínio, se você configurar) por
WhatsApp direto pra ela. Não coloque esse link em nenhum lugar do menu, do
rodapé, do Instagram ou de qualquer página do site principal. Como nada
aponta pra ele e o `robots.txt` e a tag `noindex` pedem pro Google não
indexar, ele fica de fato invisível pra quem só está navegando pelo site.

## Se um dia você quiser login de verdade

GitHub Pages sozinho não tem como pedir senha. Se no futuro você quiser que
só a Rebeca (autenticada, não só "quem tem o link") consiga entrar, a opção
mais simples é usar o **Cloudflare Pages + Cloudflare Access** (tem plano
gratuito para poucos usuários): você hospeda o mesmo `index.html` lá, e o
Cloudflare pede um código por e-mail antes de mostrar a página. Isso já é um
projeto à parte, mas fica registrado aqui caso vire uma necessidade real mais
pra frente, por exemplo quando você tiver vários alunos com o próprio ELO
PATH.
