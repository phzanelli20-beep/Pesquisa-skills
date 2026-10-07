# Pesquisa de skills do Claude Code para a equipe do Pedro

**Data da pesquisa:** 7 de outubro de 2026
**Feita por:** Claude Code, em ambiente na nuvem, só lendo e sem instalar nem executar nada das skills

---

## Resumo em 5 linhas

1. **Achei 28 skills boas**, de 9 fontes. A maioria vem da Anthropic, da Microsoft, do criador do Obsidian e da Trail of Bits. Mais **13 descartadas**, explicadas no fim.
2. **As 3 melhores para o Pedro:** `skill-creator` (Anthropic: cria e *testa* skills), `outreach-composer` (Anthropic: mensagens de venda "com a voz do dono", sempre com aprovação antes de enviar) e `playwright-cli` (Microsoft: automação do Chrome com permissões estreitas).
3. **Temas sem boa skill pronta:** Vendizap, WhatsApp no Windows de forma segura, Instagram, voz em pt-BR e segurança do próprio PC Windows. Estão em "Lacunas" e são candidatas a vocês mesmos escreverem.
4. **Maior risco encontrado:** o plugin `deep-research`, listado no **marketplace comunitário oficial da Anthropic**, está fixado num commit feito por uma terceira pessoa com a marca "PoC" (prova de conceito, termo usado em demonstrações de ataque). O autor original mudou de conta, e o roteiro de instalação manda o agente baixar de *outro* endereço e mexer no `settings.json`. **Não instalar.**
5. **Regra de ouro que saiu da pesquisa:** só instalar skill de fonte original, fixada num commit, lida antes, e de preferência sem scripts. Um estudo da Snyk achou falha crítica em 13,4% das skills de diretórios públicos (visto em terceiros).

---

## Como ler este relatório

- **"Lido no original"** quer dizer que eu clonei o repositório oficial no GitHub (só leitura), li o `SKILL.md` e rodei uma **varredura automática de todos os arquivos** da pasta da skill. A varredura procura: comandos de rede, execução de comandos, base64, caracteres invisíveis, arquivos compactados, pedidos para desligar proteção, acesso a pastas sensíveis e frases como "ignore as instruções". Foi feita com um script meu que **não executa** nada da skill.
- **"Visto em terceiros"** quer dizer que li só em resumo de busca, blog ou diretório, sem acesso ao original.
- **Nota parcial** quer dizer que não li à mão todos os scripts da skill. A varredura passou por todos os arquivos, mas a leitura humana foi do `SKILL.md` e de trechos dos scripts.
- **Estrelas:** lidas na página pública do GitHub em 07/10/2026 por um leitor automático (a API do GitHub estava bloqueada neste ambiente). São do **repositório inteiro**, não da skill.
- **Tamanho:**
  - "Descrição" é quantos caracteres a skill ocupa em **toda** conversa, porque a descrição fica sempre carregada.
  - "Corpo" é o tamanho do `SKILL.md`, que só é carregado quando a skill é usada.
  - Pela documentação, as descrições somadas são cortadas em **1.536 caracteres por skill** na lista que o Claude vê ([docs Claude Code](https://code.claude.com/docs/en/skills), lido no original). O guia oficial pede corpo com **menos de 500 linhas** ([best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices), lido no original).
- **Siglas:**
  - MCP (Model Context Protocol) é o jeito padrão de ligar o Claude a um serviço externo.
  - CLI (Command-Line Interface) é um programa de terminal.
  - LGPD é a Lei Geral de Proteção de Dados.
  - PR (pull request) é um pedido de mudança no GitHub.
  - `allowed-tools` é o campo que deixa a skill usar ferramentas sem pedir permissão.

**Minha suposição sobre os papéis das IAs** (não recebi a descrição de cada uma; ajuste se estiver errado):

| IA | Papel que assumi |
|---|---|
| Maestro | coordena a equipe e cria/ajusta skills |
| Andrea / Vigia | atendimento e conversas no WhatsApp |
| Jarvis | automação de navegador e do PC |
| Nexus | painéis em Python e dados |
| Guardião | segurança do PC e do código |
| Obsidian | notas e organização |
| Shoppe | loja Vendizap, vendas, páginas da loja |

---

## Tabela-resumo (ordenada pela utilidade)

Dentro da mesma nota, a ordem segue minha prioridade para o Pedro. As 10 primeiras são o Top 10.

| # | Skill | Fonte | Tema | IA | Utilidade (1-5) | Risco | Recomendo |
|---|---|---|---|---|---|---|---|
| 1 | `skill-creator` | Anthropic (oficial) | 3. Escrever/testar skills | Maestro | 5 | Médio (scripts) | **usar** |
| 2 | `outreach-composer` | Anthropic (knowledge-work-plugins) | 9. Mensagens de venda | Shoppe, Andrea | 5 | Baixo | **adaptar** |
| 3 | `playwright-cli` | Microsoft | 2. Navegador/testes | Jarvis | 5 | Médio (instala CLI) | **usar** |
| 4 | `frontend-design` | Anthropic (oficial) | 1. Páginas com bom design | Shoppe | 5 | Muito baixo | **usar** |
| 5 | `obsidian-markdown` | kepano (criador do Obsidian) | 6. Notas | Obsidian | 5 | Muito baixo | **usar** |
| 6 | `developing-with-streamlit` | Streamlit (oficial, dentro do pacote) | 5. Painéis Python | Nexus | 4 | Baixo | **usar** |
| 7 | `claude-security` | Anthropic (plugin oficial) | 8. Segurança/revisão | Guardião | 4 | Médio (custo, licença fechada) | **usar** |
| 8 | `powershell-expert` | hmohamed01 (comunidade) | 4. PowerShell | Guardião, Jarvis | 4 | Baixo | **adaptar** |
| 9 | `webapp-testing` | Anthropic (oficial) | 2. Testes / 5. Painéis | Nexus, Jarvis | 4 | Médio (shell) | **usar** |
| 10 | `draft-response` | Anthropic (knowledge-work-plugins) | 9. Atendimento | Andrea/Vigia | 4 | Muito baixo | **adaptar** |
| 11 | `security-guidance` (plugin de *hooks*, não é skill) | Anthropic (oficial) | 8. Segurança | Guardião | 4 | Médio (instala SDK, chama API) | **usar** |
| 12 | `copywriting` | Corey Haines (comunidade) | 9. Textos de venda / 1. Páginas | Shoppe | 4 | Baixo | **adaptar** |
| 13 | `modern-python` | Trail of Bits | 5. Python | Nexus | 4 | Médio (instalador `irm \| iex` na referência) | **adaptar** |
| 14 | `obsidian-cli` | kepano | 6. Notas | Obsidian | 4 | Médio (pode rodar JavaScript no app) | **adaptar** |
| 15 | `defuddle` | kepano | 7. Pesquisa → notas | Obsidian, Maestro | 4 | Baixo (instala CLI) | **adaptar** |
| 16 | `writing-skills` | obra/superpowers | 3. Escrever/testar skills | Maestro | 4 | Baixo | **adaptar** |
| 17 | `sharp-edges` | Trail of Bits | 8. Revisão de código | Guardião | 3 | Muito baixo (só leitura) | **usar** |
| 18 | `knowledge-synthesis` | Anthropic (knowledge-work-plugins) | 7. Resumo de fontes | Maestro, Obsidian | 3 | Muito baixo | **adaptar** |
| 19 | `sms` (parte WhatsApp) | Corey Haines | 9. WhatsApp marketing | Andrea, Shoppe | 3 | Baixo | **adaptar** |
| 20 | `ux-copy` | Anthropic (knowledge-work-plugins) | 1. Páginas / 9. Textos curtos | Shoppe | 3 | Muito baixo | **usar** |
| 21 | `claude-md-improver` | Anthropic (plugin oficial) | 3. Organização das IAs | Maestro | 3 | Baixo | **usar** |
| 22 | `obsidian-bases` | kepano | 6. Notas | Obsidian | 3 | Muito baixo | **usar** |
| 23 | `web-design-guidelines` | Vercel | 1. Páginas | Shoppe | 3 | Médio (baixa regras da internet a cada uso) | **adaptar** |
| 24 | `mcp-builder` | Anthropic (oficial) | Lacunas (conector Vendizap) | Maestro | 3 | Médio (scripts) | **só observar** |
| 25 | `differential-review` | Trail of Bits | 8. Revisão de mudanças | Guardião | 3 | Médio (Bash liberado) | **só observar** |
| 26 | `supply-chain-risk-auditor` | Trail of Bits | 8. Dependências | Guardião, Nexus | 3 | Médio (Bash liberado, consulta serviços públicos) | **só observar** |
| 27 | `inventory-planner` | Anthropic (knowledge-work-plugins) | Estoque de relógios | Shoppe | 3 | Baixo | **só observar** |
| 28 | `reactivate` | Anthropic (knowledge-work-plugins) | Clientes sumidos | Shoppe, Andrea | 3 | Baixo | **só observar** |

**Tema 10 (documentos e planilhas):** não achei nada melhor que as skills de Word, PDF, PowerPoint e Excel que vocês já têm, que são as próprias da Anthropic. A única alternativa oficial, `doc-coauthoring`, foi descartada (veja abaixo).

---

## Fichas das skills, por tema

> Padrão de cada ficha: links, versão, licença, data, estrelas, o que faz, por que serve, IA, tamanho, nota de risco e recomendação.
> Nota de risco, sempre nesta ordem: **(a)** tem scripts? **(b)** executa comandos? **(c)** baixa algo ou manda dados para fora? **(d)** `allowed-tools` amplo? **(e)** pede para desligar proteção ou instalar algo "de setup"? **(f)** código escondido? **(g)** lê pastas fora do assunto?

### Tema 1 — Páginas web e landing pages com bom design

#### 4. `frontend-design` (Anthropic), lido no original
- **Repositório:** https://github.com/anthropics/skills · **Pasta:** https://github.com/anthropics/skills/tree/main/skills/frontend-design
- **Commit da pasta:** `41bbe19d1a1a7eaab5e7bb9050a417e5c6cffc8f` (03/09/2026). Repositório lido no commit `683bc88e56f3e09ba94f7055977f3d3aa499f202` (05/10/2026).
- **Licença:** Apache 2.0 (`LICENSE.txt` na pasta) · **Estrelas:** 180 mil no repositório (página do GitHub)
- **O que faz:** orienta o Claude a fazer páginas com identidade visual própria (tipografia, cores, layout) e lista os "vícios" de página feita por IA que ele deve evitar (fundo creme com destaque terracota, numeração 01/02/03 sem motivo, animação em todo card).
- **Por que serve ao Pedro:** landing page de promoção de relógios e página "quem somos" da loja, com cara de loja de relógios e não de modelo genérico.
- **IA:** Shoppe
- **Tamanho:** descrição com cerca de 204 caracteres; corpo com 72 linhas (cerca de 9,4 mil caracteres). Leve.
- **Risco:** (a) não · (b) não · (c) não · (d) não declara · (e) não · (f) não · (g) não. Leitura completa (só 2 arquivos).
- **Observação:** é idêntica à cópia em `anthropics/claude-plugins-official/plugins/frontend-design` (comparei byte a byte). Instale só uma.
- **Utilidade:** 5 · **Recomendo: usar**

#### 20. `ux-copy` (Anthropic, plugin `design`), lido no original
- **Repositório:** https://github.com/anthropics/knowledge-work-plugins · **Pasta:** https://github.com/anthropics/knowledge-work-plugins/tree/main/design/skills/ux-copy
- **Commit da pasta:** `2d6f7e22dd25593f0f748010430ef86f19659735` (13/03/2026). Repositório em `8444efcd48f7012f09797778a36a33e73d0861f4` (01/10/2026).
- **Licença:** Apache 2.0 (raiz do repositório) · **Estrelas:** 27 mil no repositório
- **O que faz:** escreve ou revisa textos curtos de tela: botões, mensagens de erro, telas vazias, confirmações.
- **Por que serve ao Pedro:** texto dos botões e avisos da página da loja ("Comprar pelo WhatsApp", "Produto esgotado"). Serve também para respostas rápidas padronizadas.
- **IA:** Shoppe
- **Tamanho:** descrição com cerca de 269 caracteres; corpo com 108 linhas.
- **Risco:** (a) não · (b) não · (c) não · (d) não · (e) não · (f) não · (g) não. Leitura completa (1 arquivo).
- **Utilidade:** 3 · **Recomendo: usar** (pedir saída em pt-BR)

#### 23. `web-design-guidelines` (Vercel), lido no original
- **Repositório:** https://github.com/vercel-labs/agent-skills · **Pasta:** https://github.com/vercel-labs/agent-skills/tree/main/skills/web-design-guidelines
- **Commit da pasta:** `ba46938889d4e58635362fb8f618e1178ac3ec46` (16/01/2026). Repositório em `063bee94c3f4df8453406c830b0a7df0f2860278` (28/08/2026).
- **Licença:** MIT, declarada no README. **Não há arquivo LICENSE na raiz.** · **Estrelas:** 32 mil
- **O que faz:** revisa o código de uma página contra cerca de 100 regras de acessibilidade, desempenho e experiência do usuário.
- **Por que serve ao Pedro:** conferir a landing page antes de publicar (contraste, celular, botões clicáveis).
- **IA:** Shoppe
- **Tamanho:** descrição com cerca de 184 caracteres; corpo com 40 linhas.
- **Risco:** (a) não · (b) não · (c) **sim: a cada uso baixa as regras de** `raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md` e as segue como instrução · (d) não · (e) não · (f) não · (g) não. Leitura completa.
- **Por que "adaptar":** instrução que vem da internet a cada uso pode mudar sem aviso, e é exatamente o tipo de porta de entrada que o paper SKILL-INJECT descreve. Baixe as regras **uma vez**, leia, guarde dentro da skill e tire o passo de download.
- **Utilidade:** 3 · **Recomendo: adaptar**

> O `copywriting` (ficha 12) também serve para o texto da landing page.

### Tema 2 — Automação de navegador e testes (Playwright)

#### 3. `playwright-cli` (Microsoft), lido no original
- **Repositório:** https://github.com/microsoft/playwright-cli · **Pasta:** https://github.com/microsoft/playwright-cli/tree/main/skills/playwright-cli
- **Commit da pasta:** `83368cb3bfc0b2bd8ff8af4ade8e0107461ed421` (28/09/2026). Repositório em `b85c7a736bb473bf55b584e54a09ffa698d6d871`.
- **Licença:** Apache 2.0 · **Estrelas:** 13,9 mil
- **O que faz:** ensina o Claude a abrir o navegador, clicar, preencher, tirar print e gravar testes com comandos curtos (`playwright-cli click e15`), lendo um "retrato" da página em vez de despejar o HTML inteiro. Assim gasta bem menos texto.
- **Por que serve ao Pedro:** o Jarvis já automatiza o Chrome com Playwright. Esta skill é a forma oficial e econômica de fazer isso, e a própria Microsoft a recomenda para agentes de código. Também pode salvar e restaurar sessão (cookies) para não precisar logar toda vez.
- **IA:** Jarvis
- **Tamanho:** descrição com só 77 caracteres (curta demais: diz o que faz, mas não diz quando usar; perde meio ponto); corpo com 490 linhas (no limite) e 10 arquivos de referência.
- **Windows:** tem seção própria para Windows, ensinando que `&` em URL quebra no PowerShell e mostrando como escapar.
- **Risco:** (a) não tem scripts · (b) sim, roda `playwright-cli` e `npx playwright` · (c) sim: se o CLI não existir, manda instalar `npm install -g @playwright/cli@latest` (versão "latest", sem fixar) · (d) **não: o `allowed-tools` é estreito** (`Bash(playwright-cli:*)`, `Bash(npx playwright:*)`) · (e) não · (f) não · (g) a parte de "storage state" lê e salva cookies do navegador, então **guarde esses arquivos fora de pastas sincronizadas** · Nota parcial: li o `SKILL.md`; das referências, só a varredura.
- **Utilidade:** 5 · **Recomendo: usar** (instale o CLI uma vez, com versão fixa, em vez de deixar a skill instalar "latest")

#### 9. `webapp-testing` (Anthropic), lido no original
- **Repositório:** https://github.com/anthropics/skills · **Pasta:** https://github.com/anthropics/skills/tree/main/skills/webapp-testing
- **Commit da pasta:** `b9e19e6f44773509fbdd7001d77ff41a49a486c1` (20/04/2026).
- **Licença:** Apache 2.0 · **Estrelas:** 180 mil no repositório
- **O que faz:** testa aplicações web locais com scripts Python + Playwright. O `with_server.py` sobe o servidor, espera ficar pronto, roda o teste e derruba o servidor.
- **Por que serve ao Pedro:** testar os painéis Python (Streamlit/Flask) do Nexus antes de mostrar: abre, tira print, confere se o gráfico carregou.
- **IA:** Nexus, Jarvis
- **Tamanho:** descrição com cerca de 204 caracteres; corpo com 96 linhas.
- **Windows:** os exemplos usam `/tmp/...` para salvar prints. No Windows, troque por uma pasta do projeto.
- **Risco:** (a) sim, 4 arquivos Python · (b) sim: `with_server.py` usa `subprocess.Popen(..., shell=True)`, ou seja, roda o comando de servidor que você passar · (c) não · (d) não declara · (e) não · (f) não · (g) não. **Atenção:** o texto manda "não ler o código dos scripts antes de rodar". Prefira ler; são curtos. Nota parcial (li `with_server.py` em parte).
- **Utilidade:** 4 · **Recomendo: usar**

### Tema 3 — Escrita de skills, testes e avaliação de skills

#### 1. `skill-creator` (Anthropic), lido no original
- **Repositório:** https://github.com/anthropics/skills · **Pasta:** https://github.com/anthropics/skills/tree/main/skills/skill-creator
- **Commit da pasta:** `b9e19e6f44773509fbdd7001d77ff41a49a486c1` (20/04/2026). É idêntica à cópia em `anthropics/claude-plugins-official/plugins/skill-creator` (comparei byte a byte).
- **Licença:** Apache 2.0 (`LICENSE.txt` na pasta) · **Estrelas:** 180 mil no repositório
- **O que faz:** cria e melhora skills **com teste**. Escreve casos de teste, roda a skill contra eles, mostra os resultados numa página para você avaliar, mede se a descrição "dispara" na hora certa e reescreve a descrição até acertar.
- **Por que serve ao Pedro (e por que é melhor que a "criar skill a partir da conversa" de vocês):** a de vocês *gera* a skill. Esta *gera e prova* que funciona. Exemplo: antes de confiar na skill de cadastro na Vendizap, dá para escrever 5 pedidos reais ("cadastra esse Rolex da foto com preço X") e ver se a skill acerta todos.
- **IA:** Maestro
- **Tamanho:** descrição com cerca de 319 caracteres; corpo com **486 linhas** (perto do limite de 500, cerca de 33 mil caracteres). É pesada quando abre, mas só abre quando você for criar skill.
- **Windows:** usa `/tmp/` e o comando `open` (que é de Mac) para abrir o relatório. No Windows, peça para salvar o HTML numa pasta e abrir com `start`. A otimização de descrição chama `claude -p` (funciona no Claude Code).
- **Risco:** (a) sim, 10 scripts Python · (b) sim, chama `claude -p` como subprocesso (gasta tokens da sua conta) · (c) não manda dados para terceiros (só para a própria API do Claude, via `claude -p`) · (d) não declara · (e) não · (f) base64 aparece só para embutir imagens no relatório HTML (legítimo) · (g) não · Nota parcial (scripts não lidos inteiros).
- **Utilidade:** 5 · **Recomendo: usar**

#### 16. `writing-skills` (obra/superpowers), lido no original
- **Repositório:** https://github.com/obra/superpowers · **Pasta:** https://github.com/obra/superpowers/tree/main/skills/writing-skills
- **Commit da pasta:** `5bf4e78011075bcfc0dc295f0724994cd123ee71` (18/09/2026). Repositório em `8ca22dba9a94f28898bbce59f2537ff4d87c747d`.
- **Licença:** MIT · **Estrelas:** 296 mil segundo o leitor automático. O número parece alto; confira na página.
- **O que faz:** trata escrever skill como "teste primeiro". Você roda a tarefa **sem** a skill, vê o agente errar, escreve a skill e confirma que o erro sumiu. Ensina também a "fechar brechas" de racionalização do agente.
- **Por que serve ao Pedro:** é o melhor texto que achei sobre *como pensar* uma skill. O Maestro pode usá-lo como método, junto com o `skill-creator`.
- **IA:** Maestro
- **Tamanho:** descrição com 97 caracteres (boa, diz quando usar); corpo com **682 linhas, acima do limite de 500 (perde ponto)**. Depende de outra skill do mesmo pacote ("REQUIRED BACKGROUND: test-driven-development") e traz uma cópia do guia oficial da Anthropic.
- **Risco:** (a) sim, 1 script (`render-graphs.js`, que gera diagramas) · (b) sim, chama um programa externo de diagramas · (c) não · (d) não · (e) não · (f) não · (g) não · Nota parcial.
- **Utilidade:** 4 · **Recomendo: adaptar** (use como leitura de método; não instale o pacote inteiro do superpowers, veja "Descartadas")

#### 21. `claude-md-improver` (Anthropic, plugin `claude-md-management`), lido no original
- **Repositório:** https://github.com/anthropics/claude-plugins-official · **Pasta:** https://github.com/anthropics/claude-plugins-official/tree/main/plugins/claude-md-management/skills/claude-md-improver
- **Commit da pasta:** `a86e34672c44fa1fb1ae2b2c4143abcf26612ace` (16/01/2026). A pasta tem quase 9 meses sem mudança, mas o repositório é mantido (último commit em 07/10/2026, `6eb6a30bf024b182d418d3bbd11f156e360365af`).
- **Licença:** Apache 2.0 (LICENSE no plugin) · **Estrelas:** 37,5 mil no repositório
- **O que faz:** procura todos os `CLAUDE.md` (a "memória" de cada projeto), dá nota de qualidade e propõe correções pontuais.
- **Por que serve ao Pedro:** cada IA da equipe deve ter seu `CLAUDE.md`. Esta skill mantém esses arquivos curtos e atualizados.
- **IA:** Maestro
- **Tamanho:** descrição com cerca de 338 caracteres; corpo com 180 linhas.
- **Risco:** (a) não · (b) não · (c) não · (d) não · (e) não (o `npm install` que aparece é um exemplo de texto) · (f) não · (g) varre o repositório atrás de `CLAUDE.md`, o que é o assunto dela. Leitura completa por varredura; `SKILL.md` lido em parte.
- **Utilidade:** 3 · **Recomendo: usar**

### Tema 4 — PowerShell e scripts seguros no Windows

#### 8. `powershell-expert` (hmohamed01, comunidade), lido no original
- **Repositório:** https://github.com/hmohamed01/powershell-expert · **Pasta:** https://github.com/hmohamed01/powershell-expert/tree/main/powershell-expert
- **Commit:** `66b07cd612f2fbb6234eefb8cf31d1a33ee7bdf1` (12/09/2026)
- **Licença:** **MIT só declarada no README; não existe arquivo LICENSE** (pede-se a correção ao autor) · **Estrelas:** 50
- **O que faz:** escreve scripts e módulos PowerShell no padrão da Microsoft: `[CmdletBinding()]`, validação de parâmetros, `-WhatIf` e `ShouldProcess` (confirmação antes de apagar), tratamento de erro e interfaces gráficas simples (WinForms/WPF).
- **Por que serve ao Pedro:** é a única skill decente de PowerShell que achei no original. Ajuda nos scripts de limpeza e backup do PC e nos atalhos que o Jarvis roda. O padrão `-WhatIf` é ótimo para o Guardião ("mostre o que vai apagar antes de apagar").
- **IA:** Guardião, Jarvis
- **Tamanho:** descrição com cerca de 454 caracteres; corpo com 287 linhas.
- **Risco:** (a) sim, 1 script `Search-Gallery.ps1` (lido inteiro: só *pesquisa* módulos na PowerShell Gallery, não instala) · (b) sim, só busca · (c) consulta a PowerShell Gallery e a documentação da Microsoft · (d) não declara · (e) as referências mostram exemplos de `Install-PSResource ... -TrustRepository` e `-Force`. Não são ordens, mas **não deixe o agente instalar módulos sozinho** · (f) há um `powershell-expert.skill`, que é um zip **sem senha**. Conferi: o `SKILL.md` de dentro é idêntico ao da pasta · (g) não. Leitura quase completa.
- **Utilidade:** 4 · **Recomendo: adaptar** (acrescente regras de vocês: nunca usar `-ExecutionPolicy Bypass`, sempre `-WhatIf` primeiro, nunca `irm ... | iex`)

### Tema 5 — Python para painéis e pequenos servidores

#### 6. `developing-with-streamlit` (Streamlit, oficial), lido no original
- **Repositório:** https://github.com/streamlit/streamlit · **Pasta:** https://github.com/streamlit/streamlit/tree/develop/lib/streamlit/.agents/skills/developing-with-streamlit (o nome do ramo principal não foi verificado; o link usa `develop`)
- **Commit da pasta:** `54a724829e56d07a5f46fc753943640fbc9ec778` (07/10/2026)
- **Licença:** Apache 2.0 · **Estrelas:** não verificado para `streamlit/streamlit`. O repositório antigo `streamlit/agent-skills` tem 223 e foi **arquivado em 23/07/2026**, porque a skill passou a vir dentro do pacote (versão 1.58+ tem o comando `streamlit skills`).
- **O que faz:** guia oficial para criar e embelezar painéis Streamlit, com referências por assunto (dashboards, temas, layout, cache, desempenho) e modelos prontos de painel e tema.
- **Por que serve ao Pedro:** painel de vendas de relógios e de leads do Nexus, feito no padrão do próprio fabricante e atualizado junto com a versão instalada.
- **IA:** Nexus
- **Tamanho:** descrição com cerca de 490 caracteres e um "**[REQUIRED]**" exagerado no começo; corpo com 251 linhas e 55 arquivos de apoio.
- **Risco:** (a) os "scripts" são modelos de painel `.py` (exemplos) · (b) a referência de testes mostra `subprocess.Popen(["streamlit","run","app.py"])` · (c) mostra `pip install` como instrução · (d) não · (e) não · (f) não · (g) não · Nota parcial (referências só por varredura).
- **Utilidade:** 4 · **Recomendo: usar** (pelo comando `streamlit skills` da versão instalada, não pelo repositório arquivado)

#### 13. `modern-python` (Trail of Bits), lido no original
- **Repositório:** https://github.com/trailofbits/skills · **Pasta:** https://github.com/trailofbits/skills/tree/main/plugins/modern-python/skills/modern-python
- **Commit da pasta:** `123037ec8aed26f0d86327cc39137ee5043e5deb` (16/09/2026). Repositório em `82fe8226252622fa807643bdca1710901198553a`.
- **Licença:** CC BY-SA 4.0 (Creative Commons com atribuição e compartilhamento igual) · **Estrelas:** 7,4 mil
- **O que faz:** monta projetos Python com ferramentas modernas: `uv` para ambientes e pacotes, `ruff` para estilo e `ty` para tipos. Inclui scripts avulsos com dependências declaradas no próprio arquivo.
- **Por que serve ao Pedro:** organizar os painéis e servidores pequenos de forma que rodem igual em qualquer PC, sem "funcionava ontem".
- **IA:** Nexus
- **Tamanho:** descrição com cerca de 159 caracteres; corpo com 334 linhas.
- **Risco:** (a) não · (b) sim, comandos `uv` · (c) sim, `uv` baixa pacotes · (d) não · (e) **sim: a referência `uv-commands.md` mostra o instalador oficial do uv no Windows com** `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"` (baixa e executa da internet, desligando a política de execução). **Instale o uv à mão, pelo `winget`, e apague essa linha** · (f) não · (g) não. Nota parcial.
- **Utilidade:** 4 · **Recomendo: adaptar**

> O `webapp-testing` (ficha 9) completa este tema: serve para testar os painéis.

### Tema 6 — Obsidian / notas em Markdown

Todas as skills deste tema são do repositório oficial do criador do Obsidian, Steph Ango (kepano).
**Repositório:** https://github.com/kepano/obsidian-skills · lido em `3ccff5338ea700537839b21900aa5358a0402c98` (15/09/2026) · **Licença:** MIT · **Estrelas:** 49,2 mil

#### 5. `obsidian-markdown`, lido no original
- **Pasta:** https://github.com/kepano/obsidian-skills/tree/main/skills/obsidian-markdown · **Commit da pasta:** `d790939c3e631d12c3047533fddaa7c0e0218304` (22/03/2026)
- **O que faz:** ensina o "Markdown do Obsidian": `[[links]]`, embutidos, *callouts*, propriedades (frontmatter), tags.
- **Por que serve ao Pedro:** a IA Obsidian passa a criar notas de lead, de produto e de reunião que funcionam direito no cofre, com links entre cliente, relógio e conversa.
- **IA:** Obsidian
- **Tamanho:** descrição com cerca de 262 caracteres; corpo com 197 linhas.
- **Risco:** (a) não · (b) não · (c) não · (d) não · (e) não · (f) não · (g) não. Leitura completa por varredura.
- **Utilidade:** 5 · **Recomendo: usar**

#### 14. `obsidian-cli`, lido no original
- **Pasta:** https://github.com/kepano/obsidian-skills/tree/main/skills/obsidian-cli · **Commit da pasta:** `5a557ceba792fcb4c58591f3117c6887810d8df1` (25/02/2026; a pasta está parada, mas o repositório é ativo)
- **O que faz:** usa o comando `obsidian` (CLI oficial) para ler, criar, buscar e mover notas e tarefas com o Obsidian aberto.
- **Por que serve ao Pedro:** buscar "todas as notas do lead Fulano" ou criar a tarefa do dia sem abrir a janela.
- **IA:** Obsidian
- **Tamanho:** descrição com cerca de 467 caracteres; corpo com 107 linhas.
- **Risco:** (a) não · (b) sim, o CLI · (c) não · (d) não · (e) não · (f) não · (g) **inclui `obsidian eval code=...`, que roda JavaScript dentro do Obsidian e tem acesso ao cofre inteiro e aos plugins**. Para uso de notas, remova a parte de "desenvolvimento de plugins" da skill. Leitura completa.
- **Windows:** o CLI do Obsidian para Windows **não foi verificado** por mim.
- **Utilidade:** 4 · **Recomendo: adaptar**

#### 15. `defuddle`, lido no original
- **Pasta:** https://github.com/kepano/obsidian-skills/tree/main/skills/defuddle · **Commit da pasta:** `957c634e069c256270540d3f068b890cf2388b54` (09/09/2026)
- **O que faz:** transforma uma página da web em Markdown limpo (sem menu nem propaganda) com o CLI `defuddle`.
- **Por que serve ao Pedro:** salvar no Obsidian uma página de fornecedor, uma ficha técnica de relógio ou um artigo de pesquisa já limpos e com o link de origem.
- **IA:** Obsidian, Maestro
- **Tamanho:** descrição com **só 57 caracteres (vaga: não diz quando usar; perde ponto)**; corpo com 42 linhas.
- **Risco:** (a) não · (b) sim, o CLI · (c) sim, acessa a página pedida e manda instalar `npm install -g defuddle` · (d) não · (e) instalação global · (f) não · (g) não. Leitura completa.
- **Utilidade:** 4 · **Recomendo: adaptar** (melhore a descrição: "Use quando o usuário pedir para salvar/limpar uma página da web como nota")

#### 22. `obsidian-bases`, lido no original
- **Pasta:** https://github.com/kepano/obsidian-skills/tree/main/skills/obsidian-bases · **Commit da pasta:** `9b736ba8da230341054cc668bedc0bcb041baa98` (07/04/2026)
- **O que faz:** cria as "Bases" do Obsidian (`.base`), que são tabelas ou cartões filtrados de notas, como uma planilha das suas notas.
- **Por que serve ao Pedro:** visão de leads por status ou de relógios por marca direto no Obsidian.
- **IA:** Obsidian
- **Tamanho:** descrição com cerca de 256 caracteres; corpo com **500 linhas (no limite)**.
- **Risco:** todos os sete itens: não. Leitura completa por varredura.
- **Utilidade:** 3 · **Recomendo: usar** (só se usarem Bases)

> Também existe a `json-canvas` (quadros visuais `.canvas`) no mesmo repositório. É útil, mas menos ligada às tarefas do Pedro.

### Tema 7 — Pesquisa e resumo de fontes

#### 18. `knowledge-synthesis` (Anthropic, plugin `enterprise-search`), lido no original
- **Repositório:** https://github.com/anthropics/knowledge-work-plugins · **Pasta:** https://github.com/anthropics/knowledge-work-plugins/tree/main/enterprise-search/skills/knowledge-synthesis
- **Commit da pasta:** `2d6f7e22dd25593f0f748010430ef86f19659735` (13/03/2026) · **Licença:** Apache 2.0 · **Estrelas:** 27 mil no repositório
- **O que faz:** junta resultados de várias fontes numa resposta só, sem repetição, **com a fonte de cada afirmação**. Dá peso por atualidade e autoridade e marca o grau de confiança.
- **Por que serve ao Pedro:** pesquisar um fornecedor, uma marca de relógio ou um concorrente e receber resumo com fonte, pronto para virar nota.
- **IA:** Maestro, Obsidian
- **Tamanho:** descrição com cerca de 213 caracteres; corpo com 259 linhas.
- **Risco:** todos os sete itens: não (instruções em texto). Leitura completa por varredura.
- **Observação:** foi feita para o plugin de "busca na empresa" (Slack, Notion etc.). Use só o método de síntese.
- **Utilidade:** 3 · **Recomendo: adaptar**

> O `defuddle` (ficha 15) completa este tema: limpa a página antes de resumir.
> Nesta sessão aparece uma skill de conta chamada `deep-research` (Anthropic). Não achei a fonte pública dela, então **não avaliei**. A alternativa pública mais citada, o plugin comunitário `deep-research`, está em "Descartadas", com risco alto.

### Tema 8 — Segurança e revisão de código

#### 7. `claude-security` (Anthropic, plugin oficial), lido no original
- **Repositório:** https://github.com/anthropics/claude-plugins-official · **Pasta:** https://github.com/anthropics/claude-plugins-official/tree/main/plugins/claude-security
- **Commit da pasta:** `ca08d5e47d6402db586d37780c559a0c4c7ded9a` (25/09/2026)
- **Licença:** **proprietária da Anthropic**: pode instalar, usar e modificar para uso interno; **não pode redistribuir** · **Estrelas:** 37,5 mil no repositório
- **O que faz:** uma equipe de agentes faz papel de pesquisador de segurança. Mapeia o código, monta o "modelo de ameaças", procura falhas, **verifica cada achado de forma independente** e pode propor correções em arquivos de *patch* para você aplicar quando quiser.
- **Por que serve ao Pedro:** passar um pente-fino nos painéis Python e nos scripts de automação **antes** de expô-los na rede ou deixá-los rodando sozinhos.
- **IA:** Guardião
- **Tamanho:** descrição com cerca de 446 caracteres; corpo com 70 linhas (o resto fica em arquivos de apoio).
- **Risco:** (a) sim, scripts Python e `sh` · (b) sim · (c) não manda dados a terceiros (roda na sua sessão) · (d) **sim, `allowed-tools` grande** (`Bash(git *)`, vários agentes, `Workflow`) · (e) não · (f) não · (g) lê o repositório inteiro, que é o assunto dela. O próprio README avisa para rodar repositórios **de terceiros** dentro de *sandbox* (caixa isolada). **Custo:** pede confirmação de tempo e tokens antes de cada varredura. Nota parcial (scripts não lidos inteiros).
- **Windows:** os *hooks* chamam `sh`. No Windows funcionam se o Git for Windows estiver instalado; isso não foi testado por mim.
- **Utilidade:** 4 · **Recomendo: usar** (sob demanda, só no código de vocês)

#### 11. `security-guidance` (Anthropic, plugin oficial: *hooks*, não é skill), lido no original
- **Pasta:** https://github.com/anthropics/claude-plugins-official/tree/main/plugins/security-guidance · **Commit:** `a22217bb450a6cc00d7a161566e7cc7d96dbf63a` (05/10/2026) · **Licença:** Apache 2.0 · **Estrelas:** 37,5 mil no repositório
- **O que faz:**
  - avisa na hora quando o Claude escreve um dos cerca de 25 padrões perigosos (senha no código, `pickle.load`, `innerHTML`…);
  - no fim de cada turno, manda o *diff* (as mudanças) para uma revisão rápida;
  - em cada `git commit`, roda um revisor que lê arquivos relacionados.
- **Por que serve ao Pedro:** proteção contínua enquanto as IAs escrevem código, sem precisar lembrar de pedir revisão.
- **IA:** Guardião (ligado para todas as IAs que escrevem código)
- **Tamanho:** não tem `SKILL.md` nem descrição, então não pesa na lista de skills. O custo dele é outro: uma chamada extra à API a cada turno.
- **Risco:** (a) sim, vários scripts Python · (b) sim · (c) **sim, manda o diff para a API do Claude** (mesmo fornecedor, mas **gasta tokens a cada turno**) · (d) n/a (hooks) · (e) **sim: na primeira vez cria um ambiente em `~/.claude/security/agent-sdk-venv` e faz `pip install` do SDK** · (f) não · (g) não. O código trata Windows explicitamente (encoding cp1252). Nota parcial.
- **Utilidade:** 4 · **Recomendo: usar** (fique de olho no custo)

#### 17. `sharp-edges` (Trail of Bits), lido no original
- **Pasta:** https://github.com/trailofbits/skills/tree/main/plugins/sharp-edges/skills/sharp-edges · **Commit:** `123037ec8aed26f0d86327cc39137ee5043e5deb` (16/09/2026) · **Licença:** CC BY-SA 4.0 · **Estrelas:** 7,4 mil
- **O que faz:** acha "armadilhas" de configuração e de uso de bibliotecas, como valores padrão inseguros e opções que desligam segurança sem querer.
- **Por que serve ao Pedro:** revisar configuração de servidor Python, `.env` e opções de login dos painéis.
- **IA:** Guardião
- **Tamanho:** descrição com cerca de 376 caracteres; corpo com 294 linhas.
- **Risco:** (a) não · (b) não · (c) não · (d) **não: só `Read Grep Glob` (somente leitura)** · (e) não · (f) a varredura achou caracteres invisíveis em `references/lang-swift.md`. **Conferi: é o "junta-emoji" (U+200D) de um exemplo de emoji de família. É legítimo** · (g) não.
- **Utilidade:** 3 · **Recomendo: usar**

#### 25. `differential-review` (Trail of Bits), lido no original
- **Pasta:** https://github.com/trailofbits/skills/tree/main/plugins/differential-review/skills/differential-review · **Commit:** `123037ec8aed26f0d86327cc39137ee5043e5deb` · **Licença:** CC BY-SA 4.0 · **Estrelas:** 7,4 mil no repositório
- **O que faz:** revisa uma mudança (commit ou PR) com foco em segurança: quem chama o código mudado, se há teste, se reabre falha antiga.
- **Por que serve ao Pedro:** revisar mudanças grandes nos scripts de automação. Para o volume de vocês, o `claude-security` já cobre.
- **IA:** Guardião
- **Tamanho:** descrição com cerca de 477 caracteres; corpo com 226 linhas.
- **Risco:** (a) não · (b) sim (git) · (c) não · (d) **sim, `Read Write Grep Glob Bash` (Bash livre)** · (e) não · (f) não · (g) não.
- **Utilidade:** 3 · **Recomendo: só observar**

#### 26. `supply-chain-risk-auditor` (Trail of Bits), lido no original
- **Pasta:** https://github.com/trailofbits/skills/tree/main/plugins/supply-chain-risk-auditor/skills/supply-chain-risk-auditor · **Commit:** `123037ec8aed26f0d86327cc39137ee5043e5deb` · **Licença:** CC BY-SA 4.0 · **Estrelas:** 7,4 mil no repositório
- **O que faz:** audita as dependências (bibliotecas) de um projeto: falhas conhecidas, projetos abandonados e scripts que rodam na instalação.
- **Por que serve ao Pedro:** conferir as bibliotecas dos painéis e das automações uma vez por mês.
- **IA:** Guardião, Nexus
- **Tamanho:** descrição com cerca de 367 caracteres; corpo com 123 linhas.
- **Risco:** (a) sim, scripts Python com testes · (b) sim · (c) **consulta serviços públicos** (`api.osv.dev`, `registry.npmjs.org`, `pypi.org`, `api.scorecard.dev`, GitHub) **mandando os nomes das dependências** (dado público, sem dado de cliente) · (d) **sim, `Bash` livre** · (e) não · (f) não · (g) não · Nota parcial.
- **Utilidade:** 3 · **Recomendo: só observar**

### Tema 9 — Redação curta de mensagens (WhatsApp, vendas, atendimento)

#### 2. `outreach-composer` (Anthropic, plugin `small-business`), lido no original
- **Repositório:** https://github.com/anthropics/knowledge-work-plugins · **Pasta:** https://github.com/anthropics/knowledge-work-plugins/tree/main/small-business/skills/outreach-composer
- **Commit da pasta:** `84d8efdb6e80e2b26898e5c3109d13eddde97761` (15/09/2026) · **Licença:** Apache 2.0 · **Estrelas:** 27 mil no repositório
- **O que faz:** escreve mensagens de prospecção e de *follow-up* (retorno) que "soam como o dono escreveu":
  - primeiro aprende o estilo do dono a partir de mensagens reais dele;
  - prende cada mensagem a algo específico do cliente;
  - limita a primeira mensagem a 120 palavras;
  - passa tudo por um "teste anti-robô" com mais de 100 linhas de padrões;
  - **nunca envia sem aprovação**.
- **Por que serve ao Pedro:** é exatamente o elo entre "pesquisa de lead" e "envio pelo WhatsApp" que vocês já têm. O lead chega, esta skill escreve a mensagem no tom do Pedro, ele aprova e a skill de WhatsApp envia. Também é a melhor base para o *follow-up* de quem pediu preço e sumiu.
- **IA:** Shoppe (vendas), Andrea (atendimento)
- **Tamanho:** descrição com cerca de 826 caracteres (pesa em toda conversa); corpo com 145 linhas.
- **Risco:** (a) não · (b) não · (c) `WebFetch` para ler o site do prospecto · (d) **não: só `Read, WebFetch`** · (e) não · (f) não · (g) lê arquivos compartilhados do plugin (`../../shared/voice-profile.md` etc.), que são do assunto dela. O plugin tem regras de dado pessoal ("nunca reproduzir CPF/IDs") e de moeda e país (aceita BRL). Leitura do `SKILL.md` completa.
- **Por que "adaptar":** foi pensada para e-mail e CRM (HubSpot, Gmail, Apollo). Para vocês: trocar o canal por WhatsApp, pedir saída em pt-BR, apontar o "perfil de voz" para mensagens reais do Pedro e manter o passo de aprovação. Ela depende da pasta `shared/` do plugin; copie junto ou instale o plugin `small-business` inteiro e desligue o que não usar.
- **Utilidade:** 5 · **Recomendo: adaptar**

#### 10. `draft-response` (Anthropic, plugin `customer-support`), lido no original
- **Pasta:** https://github.com/anthropics/knowledge-work-plugins/tree/main/customer-support/skills/draft-response · **Commit:** `2d6f7e22dd25593f0f748010430ef86f19659735` (13/03/2026) · **Licença:** Apache 2.0 · **Estrelas:** 27 mil no repositório
- **O que faz:** rascunha respostas ao cliente conforme a situação: dúvida de produto, atraso, notícia ruim, pedido recusado, cobrança.
- **Por que serve ao Pedro:** atendimento do WhatsApp em situações delicadas ("o relógio atrasou", "não temos esse modelo", "não fazemos esse desconto").
- **IA:** Andrea / Vigia
- **Tamanho:** descrição com cerca de 275 caracteres; corpo com 419 linhas (grande).
- **Risco:** todos os sete itens: não (texto puro). Leitura por varredura completa.
- **Utilidade:** 4 · **Recomendo: adaptar** (cortar o que é de suporte de software, pedir pt-BR e tom de WhatsApp)

#### 12. `copywriting` (Corey Haines, comunidade), lido no original
- **Repositório:** https://github.com/coreyhaines31/marketingskills · **Pasta:** https://github.com/coreyhaines31/marketingskills/tree/main/skills/copywriting
- **Commit da pasta:** `12188f1e3d3d8538fd32a96c925a8f6d7641827e` (02/10/2026) · **Licença:** MIT · **Estrelas:** 53,6 mil
- **O que faz:** escreve e melhora texto de venda: títulos, chamadas para ação, proposta de valor, páginas de produto.
- **Por que serve ao Pedro:** descrição de produto e texto da landing page de relógios. Também serve para posts.
- **IA:** Shoppe
- **Tamanho:** **descrição com cerca de 946 caracteres (muito longa: pesa em toda conversa; perde ponto)**; corpo com 287 linhas.
- **Risco:** todos os sete itens: não (texto puro). Leitura por varredura completa.
- **Observação:** o pacote tem mais de 50 skills; **não instale todas**. A irmã `copy-editing` (revisão de texto) é boa, mas tem corpo de 490 linhas.
- **Utilidade:** 4 · **Recomendo: adaptar** (encurtar a descrição e pedir pt-BR)

#### 19. `sms` (Corey Haines; tem seção de WhatsApp), lido no original
- **Pasta:** https://github.com/coreyhaines31/marketingskills/tree/main/skills/sms · **Commit:** `4a4564efbdee22b4729eca48a055bf3e177f98fa` (02/10/2026) · **Licença:** MIT · **Estrelas:** 53,6 mil no repositório
- **O que faz:** planeja fluxos de mensagem (boas-vindas, carrinho abandonado, pós-venda, reconquista). Tem referência própria de WhatsApp: janela de 24 horas, modelos aprovados, *opt-in* (consentimento), qualidade do número.
- **Por que serve ao Pedro:** organizar as mensagens automáticas de pós-venda e de reconquista sem queimar o número do WhatsApp.
- **IA:** Andrea, Shoppe
- **Tamanho:** descrição com cerca de 748 caracteres; corpo com 353 linhas.
- **Risco:** todos os sete itens: não (texto). **Atenção:** as regras legais são dos EUA (TCPA). Para o Brasil, troque pelas regras da LGPD.
- **Utilidade:** 3 · **Recomendo: adaptar**

> O `ux-copy` (ficha 20) também serve para frases curtas padronizadas.

### Outras úteis (fora dos 10 temas, ligadas à rotina do Pedro)

#### 24. `mcp-builder` (Anthropic), lido no original
- **Pasta:** https://github.com/anthropics/skills/tree/main/skills/mcp-builder · **Commit:** `b9e19e6f44773509fbdd7001d77ff41a49a486c1` (20/04/2026) · **Licença:** Apache 2.0 · **Estrelas:** 180 mil no repositório
- **O que faz:** guia para construir um servidor MCP (conector) bem feito, em Python ou Node.
- **Por que serve ao Pedro:** se um dia vocês quiserem um conector próprio para a Vendizap em vez de automação de tela, este é o guia.
- **IA:** Maestro
- **Tamanho:** descrição com cerca de 277 caracteres; corpo com 237 linhas.
- **Risco:** (a) sim, 2 scripts de avaliação · (b) sim, sobe o servidor que você criou · (c) os exemplos usam `axios` para chamar APIs · (d) não · (e) não · (f) não · (g) os exemplos leem chave de API de variável de ambiente (normal) · Nota parcial.
- **Utilidade:** 3 · **Recomendo: só observar** (até decidirem fazer o conector)

#### 27. `inventory-planner` e 28. `reactivate` (Anthropic, plugin `small-business`), lidos no original
- **Pastas:** https://github.com/anthropics/knowledge-work-plugins/tree/main/small-business/skills/inventory-planner e https://github.com/anthropics/knowledge-work-plugins/tree/main/small-business/skills/reactivate · **Commit:** `84d8efdb6e80e2b26898e5c3109d13eddde97761` (15/09/2026) · **Licença:** Apache 2.0 · **Estrelas:** 27 mil no repositório
- **O que fazem:**
  - `inventory-planner` calcula o ritmo de venda por item, a data em que vai faltar e quanto repor (aceita um CSV exportado);
  - `reactivate` acha clientes que pararam de comprar e rascunha mensagens de reconquista, enviando só o que o dono aprovar.
- **Por que servem ao Pedro:**
  - o `inventory-planner` decide quais relógios repor a partir de um CSV de vendas da Vendizap;
  - o `reactivate` recupera clientes antigos da loja.
- **IA:** Shoppe (e Andrea, no `reactivate`)
- **Tamanho:** descrições com cerca de 908 e 863 caracteres (pesadas); corpos com 127 e 110 linhas.
- **Risco:** (a) não · (b) não · (c) `WebFetch` · (d) não: `Read, WebFetch` · (e) não · (f) não · (g) não. Os dois pressupõem conectores pagos (Shopify, Square, CRM), mas funcionam com CSV ou texto colado.
- **Utilidade:** 3 cada · **Recomendo: só observar** (testar o `inventory-planner` com um CSV antes de adotar)

---

## Top 10 (com o motivo)

1. **`skill-creator`** (Anthropic): a única que *prova* que uma skill funciona antes de vocês confiarem nela. É melhor que a "criar skill a partir da conversa" que vocês já têm.
2. **`outreach-composer`** (Anthropic): mensagem de venda no tom do Pedro, com teste anti-robô e aprovação obrigatória. Fecha o ciclo lead → mensagem → WhatsApp.
3. **`playwright-cli`** (Microsoft): forma oficial e econômica de o Jarvis controlar o navegador, com permissões estreitas e notas para Windows.
4. **`frontend-design`** (Anthropic): landing pages de relógio com identidade própria, em 72 linhas e sem nenhum script.
5. **`obsidian-markdown`** (kepano): notas que funcionam de verdade no Obsidian, feita pelo criador do próprio Obsidian e sem risco.
6. **`developing-with-streamlit`** (Streamlit): painéis Python no padrão do fabricante, atualizados junto com a versão instalada.
7. **`claude-security`** (Anthropic): pente-fino de segurança sob demanda, com verificação de cada achado, antes de deixar automações rodando sozinhas.
8. **`powershell-expert`** (comunidade): a única skill de PowerShell decente no original. Ensina `-WhatIf`, o "mostre antes de apagar" de que o Guardião precisa.
9. **`webapp-testing`** (Anthropic): testa os painéis do Nexus abrindo o navegador de verdade antes de mostrar ao Pedro.
10. **`draft-response`** (Anthropic): respostas difíceis de atendimento (atraso, "não temos", desconto negado) com tom certo.

---

## Descartadas e por quê

| Skill / plugin | Fonte | Motivo | Lido no original? |
|---|---|---|---|
| **`deep-research`** (plugin comunitário) | https://github.com/oduffy-delphi/deep-research-claude | **Perigoso.** Último commit (`cfeda2830a9c9d1b47d2bedfaed0f196851a1a5d`, 24/05/2026) é de outra pessoa (John Stawinski), tem a mensagem "Add project title" e só acrescenta "**# PoC -- John Stawinski**" no README. O **marketplace comunitário oficial da Anthropic está fixado exatamente nesse commit** (conferi no `marketplace.json`, commit `f60f0454df3045f724c43c6346ec80bdcc3472b2`). O autor trocou de conta (`oduffy-delphi` → `dbc-oduffy`), e o README manda **colar um prompt para o agente instalar** de outro endereço; o roteiro de instalação manda o agente **editar `~/.claude/settings.json`** e ligar um recurso experimental. Isso é um texto mandando a IA agir, e eu não obedeci. Não afirmo que houve ataque; os fatos bastam para não instalar. | Sim |
| `claude-channel-whatsapp` | https://github.com/PenguinMiaou/claude-channel-whatsapp | Usa a biblioteca **não oficial** Baileys para se passar por WhatsApp Web (fora da API oficial do WhatsApp). Exige iniciar o Claude com `--dangerously-load-development-channels`. Roda `bun install` a cada inicialização (`"start": "bun install ... && bun server.ts"`). Guarda as credenciais da conta em `~/.claude/channels/whatsapp/auth/`. Último commit em 06/04/2026 (cerca de 6 meses). | Sim (README e package.json; `server.ts` não lido) |
| `guard` | https://github.com/TracineHQ/guard | Boa ideia (bloqueia `rm -rf`, `curl \| sh`, vazamento de credencial), mas o README diz: **"Windows is not supported in v1"**. Só funciona em Mac/Linux/WSL. | Sim |
| `windows-shell` | https://github.com/nicoforclaude/claude-windows-shell | Último commit em 27/11/2025 (mais de 10 meses). Recomenda `powershell -ExecutionPolicy Bypass -File ...`, ou seja, desligar a proteção de scripts. | Sim |
| `web-artifacts-builder` | https://github.com/anthropics/skills/tree/main/skills/web-artifacts-builder | Só `bash` (`init-artifact.sh`, `bundle-artifact.sh`), roda `npm install -g pnpm` e traz componentes num `.tar.gz` (sem senha; conferi a lista: 49 arquivos de interface). É feito para artefatos do claude.ai. **Só Mac/Linux.** | Sim |
| `doc-coauthoring` | https://github.com/anthropics/skills/tree/main/skills/doc-coauthoring | **Sem arquivo de licença na pasta** (as vizinhas têm) e parada desde 04/12/2025 (mais de 10 meses). Corpo com 376 linhas. | Sim |
| Skills de documentos `docx`, `pdf`, `pptx`, `xlsx` (repositório público) | https://github.com/anthropics/skills | Vocês já têm. A licença é **proprietária** ("source-available"): só leitura, não copiar nem adaptar. Não é descarte por qualidade. | Sim |
| `streamlit/agent-skills` | https://github.com/streamlit/agent-skills | **Arquivado** em 23/07/2026. Substituído pela versão que vem no pacote (ficha 6). | Sim |
| `frontend-design` e `skill-creator` do `claude-plugins-official` | https://github.com/anthropics/claude-plugins-official | **Duplicadas** byte a byte das do `anthropics/skills`. Instale só uma cópia. | Sim |
| `brainstorming` (superpowers) | https://github.com/obra/superpowers/tree/main/skills/brainstorming | Descrição imperativa ("**You MUST use this before any creative work**"), que faz a skill disparar em tudo. Sobe um servidor local com scripts `.sh`. | Sim |
| Pacote completo `superpowers` | https://github.com/obra/superpowers | Muda o jeito de trabalhar inteiro (git worktrees, TDD obrigatório, subagentes). É ótimo para equipe de programação, mas exagerado para a rotina do Pedro. Use só a leitura do `writing-skills`. | Sim (parcial) |
| `skill-improver` (Trail of Bits) | https://github.com/trailofbits/skills/tree/main/plugins/code-improver/skills/skill-improver | Laço autônomo que depende de outro plugin (`plugin-dev`) e de `Workflow`. Gasta muito e se sobrepõe ao `skill-creator`. | Sim |
| `social` (Corey Haines) | https://github.com/coreyhaines31/marketingskills/tree/main/skills/social | Descrição com mais de 1.000 caracteres e receitas `curl` para raspar redes sociais. Pesada e arriscada para a prospecção no Instagram (termos de uso). | Sim |

---

## Lacunas (tarefas sem boa skill pronta: candidatas a vocês escreverem)

1. **Vendizap:** nenhuma skill pública. As de vocês (cadastrar, editar, buscar no WhatsApp) são únicas. Se a Vendizap tiver API, um conector MCP seria mais robusto que automação de tela (use o `mcp-builder` como guia).
2. **WhatsApp no Windows, de forma segura:** só achei pontes não oficiais (Baileys / WhatsApp Web), com risco para a conta. A skill de envio de vocês, com aprovação humana, continua sendo o caminho. Vale escrever uma skill de **"regras de envio"**: janela de 24 horas, consentimento, limite por dia e nunca enviar sem aprovação.
3. **Prospecção no Instagram:** nada confiável no original. O que aparece envolve raspagem e esbarra nos termos de uso.
4. **Voz em pt-BR** (falar e ouvir): não achei skill boa no original. Minha busca neste tema foi curta, e só achei plugins de "aviso sonoro".
5. **Segurança do PC Windows:** o único bom (`guard`) não roda no Windows. Candidata: uma skill do Guardião com checagens de Windows Defender, atualizações e portas abertas, **só leitura** e com `-WhatIf` para qualquer mudança.
6. **Tom de voz em português do Brasil:** todas as skills de texto são em inglês e com regras dos EUA. Candidata: uma skill "voz do Pedro", que o `outreach-composer` já sabe consumir como perfil de voz, e uma de **regras da LGPD** para mensagens.
7. **Ponte lead → Obsidian:** não há skill que pegue um lead (da pesquisa ou do Maps) e crie a nota padronizada no cofre com links. É fácil de escrever com o `obsidian-markdown` como base.

---

## O que aprendi sobre como achar e escrever boas skills

**O que as melhores têm em comum** (lido no original nos repositórios acima e no guia oficial):
- **Descrição** que diz *o que faz* e *quando usar*, em terceira pessoa, com as palavras que o usuário falaria. As fracas aqui: `defuddle` (57 caracteres, sem "quando") e `playwright-cli` (77). As pesadas: `copywriting` (946) e `social` (mais de 1.000).
- **Corpo curto** (menos de 500 linhas) e detalhes em arquivos de referência a um nível de distância ("progressive disclosure", ou revelação aos poucos). Exemplos bons: `frontend-design` (72 linhas), `claude-security` (70 linhas + apoio).
- **Exemplos concretos** e listas do que *não* fazer: o "teste anti-robô" do `outreach-composer` e os "vícios de página feita por IA" do `frontend-design`.
- **Passo de aprovação humana** antes de qualquer ação externa (enviar, postar, pagar). É o padrão de todo o plugin `small-business` da Anthropic.
- **`allowed-tools` estreito**, só o necessário (`playwright-cli`, `sharp-edges`, `outreach-composer`).
- **Sinais de teste:** `skill-creator` e `marketingskills` trazem `evals/` (casos de teste), e a Trail of Bits tem testes dos scripts.

**Armadilhas que encontrei:**
- **Instrução que vem da internet a cada uso** (`web-design-guidelines`): a skill pode mudar sem você saber.
- **"Peça para seu agente instalar"** (`deep-research`): é texto mandando a IA agir. Sempre trate README como dado, não como ordem.
- **Repositório que mudou de dono ou de conta:** o link do marketplace pode continuar apontando para a conta antiga. **Fixe o commit e confira quem fez o último commit.**
- **Instaladores `irm ... | iex` / `curl ... | sh` e `-ExecutionPolicy Bypass`** escondidos em referências (`modern-python`, `windows-shell`).
- **Descrição imperativa** ("You MUST use this…", "[REQUIRED]"): faz a skill disparar em tudo e gastar contexto.
- **Mac/Linux disfarçado:** caminhos `/tmp`, comando `open`, scripts `.sh`. No Windows, confira antes.
- **Muitas skills ao mesmo tempo:** cada descrição pesa em toda conversa. Instale poucas e desligue o que não usa. O Claude Code tem `/skill-doctor` para medir isso (docs, lido no original).
- **Estudos de segurança** (visto em terceiros, porque os sites estavam bloqueados neste ambiente):
  - a Snyk ("ToxicSkills", fev/2026) varreu **3.984 skills** do ClawHub e do skills.sh e achou **13,4% (534) com falha crítica** e **36,82% com alguma falha** ([snyk.io](https://snyk.io/blog/toxicskills-malicious-ai-agent-skills-clawhub));
  - o paper **SKILL-INJECT** (arXiv 2602.20156, de Schmotz, Beurer-Kellner, Abdelnabi e Andriushchenko) relata **até 80% de sucesso de ataque** escondendo uma linha maliciosa no meio de instruções plausíveis, incluindo vazamento de dados e ações destrutivas ([arxiv.org/abs/2602.20156](https://arxiv.org/abs/2602.20156)).

**Como testar uma skill antes de adotar:**
1. Ler tudo (`SKILL.md`, referências, scripts) e procurar os 7 itens da nota de risco.
2. Fixar o commit (não usar "main" ou "latest").
3. Escrever **3 a 5 pedidos reais** da equipe e rodar com o `skill-creator`: com a skill e sem a skill.
4. Testar em **sessão nova**. Conversa velha esconde falhas (docs Claude Code).
5. Confirmar que ela aparece em `/skills`, validar com `claude plugin validate` e medir o peso com `/skill-doctor` (docs Claude Code, lido no original).
6. Para skill que age fora (enviar, apagar), usar `disable-model-invocation: true`, assim ela só roda quando alguém chamar com `/nome` (docs Claude Code).

---

## Não consegui verificar

- **arxiv.org, snyk.io, skill-inject.com e simonwillison.net:** bloqueados pela rede deste ambiente. Os números do SKILL-INJECT e da Snyk vieram de resumo de busca (visto em terceiros).
- **Reddit, Hacker News e YouTube:** bloqueados ou sem acesso. **Não li nenhum relato de fórum no original**, então a parte "o que funciona na prática" vem só de buscas e do bug de Windows citado em [claudeissues.com](https://claudeissues.com/issue/28670-bug-claude-code-repeatedly-uses-bash-syntax-extglob-on-windows-powershell-and-fa) (visto em terceiros).
- **API do GitHub:** bloqueada. As estrelas foram lidas da página por um leitor automático. **As 296 mil estrelas do `obra/superpowers` parecem altas; confira.** As estrelas do `streamlit/streamlit` não foram lidas.
- **Comando `obsidian` no Windows:** não verifiquei se o CLI do Obsidian funciona no Windows.
- **Ramo principal do `streamlit/streamlit`:** o link usa `develop`, mas não conferi o nome do ramo.
- **Scripts não lidos inteiros à mão** (nota parcial; só varredura automática):
  - `skill-creator` (10 scripts);
  - `claude-security` (scripts e hooks);
  - `security-guidance` (hooks);
  - `supply-chain-risk-auditor`;
  - `mcp-builder`;
  - `server.ts` do `claude-channel-whatsapp`.
- **Skills de PowerShell vistas só em diretórios de terceiros** e não abertas no original: "PowerShell Master", "Admin Windows", "powershell-windows" (skills.cat, openskillindex, claudemarketplaces). Por isso ficaram fora.
- **Lista comunitária** (`anthropics/claude-plugins-community`): tem **2.284 plugins**. Filtrei por palavras-chave dos temas e abri só 4. O resto **não foi avaliado**.
- **Skill de conta `deep-research` da Anthropic:** aparece nesta sessão, mas não achei fonte pública para ler.

---

## Fontes principais (todas lidas no original, salvo indicação)

- Guia oficial "Skill authoring best practices": https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices
- Documentação de skills do Claude Code: https://code.claude.com/docs/en/skills
- https://github.com/anthropics/skills (commit `683bc88e56f3e09ba94f7055977f3d3aa499f202`)
- https://github.com/anthropics/claude-plugins-official (commit `6eb6a30bf024b182d418d3bbd11f156e360365af`)
- https://github.com/anthropics/knowledge-work-plugins (commit `8444efcd48f7012f09797778a36a33e73d0861f4`)
- https://github.com/anthropics/claude-plugins-community (commit `f60f0454df3045f724c43c6346ec80bdcc3472b2`)
- https://github.com/microsoft/playwright-cli (commit `b85c7a736bb473bf55b584e54a09ffa698d6d871`)
- https://github.com/kepano/obsidian-skills (commit `3ccff5338ea700537839b21900aa5358a0402c98`)
- https://github.com/streamlit/streamlit (commit `707b3ad1bb646b0a707cdef6cb820b604d269ddb`) e https://github.com/streamlit/agent-skills (arquivado)
- https://github.com/vercel-labs/agent-skills (commit `063bee94c3f4df8453406c830b0a7df0f2860278`)
- https://github.com/obra/superpowers (commit `8ca22dba9a94f28898bbce59f2537ff4d87c747d`)
- https://github.com/trailofbits/skills (commit `82fe8226252622fa807643bdca1710901198553a`)
- https://github.com/coreyhaines31/marketingskills (commit `5e721d73ac85be8ba917d6a9ca9cb5bc98f02b80`)
- https://github.com/hmohamed01/powershell-expert (commit `66b07cd612f2fbb6234eefb8cf31d1a33ee7bdf1`)
- Descartadas abertas no original: https://github.com/oduffy-delphi/deep-research-claude, https://github.com/PenguinMiaou/claude-channel-whatsapp, https://github.com/TracineHQ/guard, https://github.com/nicoforclaude/claude-windows-shell
- Usadas só para descobrir (visto em terceiros): listas "awesome" (travisvn, ComposioHQ, hesreallyhim) e diretórios skills.sh, skills.cat, openskillindex
- Segurança (visto em terceiros): Snyk ToxicSkills (https://snyk.io/blog/toxicskills-malicious-ai-agent-skills-clawhub) e SKILL-INJECT (https://arxiv.org/abs/2602.20156)
