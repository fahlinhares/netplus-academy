# NET+ ACADEMY — CompTIA Network+ N10-009

Simulador web estático, responsivo e instalável (PWA) para preparação independente para o exame CompTIA Network+ N10-009.

## O que está incluído

- 300 questões originais em português, distribuídas em cinco domínios (60 por domínio).
- Modo estudo com explicação imediata.
- Simulados de 20, 50 e 90 questões, com cronômetro.
- Filtro por domínio.
- 10 cenários PBQ interativos introdutórios.
- Flashcards de portas, protocolos e conceitos.
- Revisão de questões erradas.
- Painel de desempenho e progresso salvo em `localStorage`.
- Interface dark e responsiva para celular.
- PWA com cache básico para acesso posterior.

## Estrutura

```text
netplus-academy/
├── index.html
├── styles.css
├── app.js
├── manifest.json
├── sw.js
├── README.md
├── .nojekyll
├── assets/
│   └── icon.svg
└── data/
    └── questions.json
```

## Executar localmente

Não abra `index.html` diretamente com `file://`, pois o navegador pode bloquear o carregamento do JSON.

### Opção 1 — VS Code

1. Abra a pasta `netplus-academy` no VS Code.
2. Instale a extensão **Live Server**.
3. Clique com o botão direito em `index.html`.
4. Selecione **Open with Live Server**.

### Opção 2 — Python

No terminal, dentro da pasta do projeto:

```bash
python -m http.server 8000
```

Acesse `http://localhost:8000`.

## Publicar no GitHub Pages

1. Entre em https://github.com e crie um repositório chamado `netplus-academy`.
2. Deixe o repositório como **Public** (GitHub Pages gratuito em repositórios públicos).
3. Extraia os arquivos deste pacote.
4. Na página do repositório, selecione **Add file → Upload files**.
5. Envie o conteúdo da pasta do projeto, incluindo `index.html`, `data/`, `assets/` e os demais arquivos. O `index.html` deve ficar na raiz do repositório.
6. Clique em **Commit changes**.
7. Abra **Settings → Pages**.
8. Em **Build and deployment**, escolha **Deploy from a branch**.
9. Selecione a branch `main` e a pasta `/(root)`, depois clique em **Save**.
10. Aguarde a publicação. O endereço será `https://SEU-USUARIO.github.io/netplus-academy/`.

A primeira publicação pode levar alguns minutos. O GitHub Pages exibirá o endereço em Settings → Pages.

## Atualizar o projeto

Edite os arquivos localmente ou diretamente no GitHub e faça commit na branch `main`. O Pages publicará a nova versão automaticamente.

## Usar no celular

1. Abra o endereço publicado no Chrome (Android) ou Safari (iPhone).
2. Android: menu do navegador → **Instalar app** ou **Adicionar à tela inicial**.
3. iPhone: botão Compartilhar → **Adicionar à Tela de Início**.

O service worker requer HTTPS ou localhost. GitHub Pages fornece HTTPS.

## Como adicionar ou editar questões

Edite `data/questions.json`. Cada questão usa esta estrutura:

```json
{
  "id": "N9-301",
  "domain": "Conceitos de redes",
  "weight": "23%",
  "difficulty": "Médio",
  "type": "multiple_choice",
  "question": "Enunciado da questão",
  "options": ["Alternativa A", "Alternativa B", "Alternativa C", "Alternativa D"],
  "answer": 1,
  "explanation": "Explicação da resposta correta.",
  "topic": "Tema"
}
```

`answer` é o índice da alternativa correta, começando em zero.

## Observações importantes

- O banco contém questões autorais de estudo, não questões oficiais nem dumps do exame.
- A distribuição inicial é uniforme (60 questões por domínio); os pesos oficiais são apresentados no painel para orientar o estudo. Os simulados aleatórios não são uma reprodução estatística perfeita do blueprint oficial.
- As 10 PBQs são cenários introdutórios de múltipla escolha; próximas versões podem incluir atividades de arrastar/soltar, associação, configuração de VLAN e subnetting interativo.
- O progresso fica no armazenamento local do navegador. Não sincroniza automaticamente entre dispositivos e pode ser apagado se os dados do navegador forem limpos.
- O PWA faz cache dos arquivos principais, mas o primeiro acesso precisa de internet.
- Para uso em produção, recomenda-se revisar tecnicamente as questões, acrescentar fontes de estudo e validar a experiência em diferentes navegadores.

## Referência oficial

Consulte sempre os objetivos de exame mais recentes no site da CompTIA:
https://www.comptia.org/certifications/network
