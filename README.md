# Leitura de ofertas (função Vercel)

Esta pasta contém a função que lê a foto de uma oferta com o Claude.

Como testar:
1. Coloque a pasta `api/` na raiz do projeto Vercel (ao lado do `index.html`).
2. Na Vercel, em Settings > Environment Variables, crie `ANTHROPIC_API_KEY` com a sua chave.
3. Faça o deploy. A função fica em `https://SEU-SITE.vercel.app/api/ler-oferta`.
4. Teste com uma foto em base64:
   curl -X POST https://SEU-SITE.vercel.app/api/ler-oferta -H "content-type: application/json" -d '{"imagem":"<base64 da foto>","tipo":"image/jpeg"}'

Resposta esperada: {"itens":[{"nome":"...","marca":"...","peso":"...","preco":0.00,"preco_de":null,"bbox":[0,0,1,1]}]}

Ainda não inclui: salvar as ofertas no banco e a alteração no index.html. Essas partes vêm depois.
