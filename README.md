# NET+ ACADEMY — CompTIA Network+ N10-009

Aplicação estática responsiva e instalável (PWA), em português, para estudar com os seis PDFs enviados.

## Conteúdo importado
- 550 registros, numerados de 001 a 550.
- Fontes: bancos PDF 01, 05, 09, 13, 17 e 21 (nomes de arquivo BQ 01 a BQ 06).
- Cada registro mantém a referência do PDF e o número original.
- Enunciados e opções têm tradução automática/glossário para termos em inglês recorrentes; siglas e nomes técnicos são preservados.
- Explicações extraídas do campo `R:` são mantidas no campo `explanation`.

## Nota importante sobre o gabarito
Os PDFs não apresentam uma chave de respostas padronizada separada em todos os itens. O conteúdo após `R:` é uma justificativa textual e frequentemente indica a resposta correta, mas nem sempre contém uma letra ou opção explicitamente marcada. Para evitar inventar respostas, os registros começam com `answer: null` e a aplicação permite consultar a justificativa e fazer autoavaliação. Há registros sem explicação no próprio PDF; esses itens ficam sinalizados. Questões com chave validada podem receber `answer` posteriormente.

## Recursos
- Busca por texto, filtros por domínio estimado e banco de origem.
- Modo estudo com justificativa.
- Simulado aleatório com autoavaliação.
- Lista de revisão persistida no navegador (localStorage).
- Layout responsivo e cache offline básico via service worker.

## Publicar no GitHub Pages
1. Envie todo o conteúdo desta pasta para a raiz do repositório `netplus-academy`.
2. Abra **Settings → Pages**.
3. Em **Build and deployment**, selecione **Deploy from a branch**.
4. Selecione `main` e `/(root)` e clique em **Save**.
5. Aguarde o deploy e acesse `https://SEU-USUARIO.github.io/netplus-academy/`.

## Testar localmente
Abra a pasta com VS Code e use Live Server. O carregamento de `data/questions.json` requer um servidor HTTP local; abrir o HTML diretamente via `file://` não é recomendado.

## Estrutura
- `index.html` — interface
- `styles.css` — tema escuro e responsivo
- `app.js` — lógica de estudo e simulado
- `data/questions.json` — banco de 550 questões
- `manifest.json`, `sw.js` — PWA
- `assets/icon.svg` — ícone

## Classificação por domínio
Os domínios são uma classificação temática inicial por palavras-chave, não uma classificação oficial validada questão por questão. Revise a taxonomia antes de usar os filtros como métrica definitiva de preparação.
