# Tráfego pago da Amo Sapatilhas: estudo completo

**Data:** 30 de outubro de 2026
**Pedido de:** Pedro · **Feito por:** Claude Code, na nuvem, só pesquisando e lendo
**Escopo:**
- **Loja:** Amo Sapatilhas, no Rio de Janeiro.
- **Plataformas:** Meta (Instagram e Facebook) e Google Ads.
- **Verba:** R$ 2.000 por mês.
- **Região:** só o RJ por enquanto.
- **Três partes:**
  1. o plano de anúncios, a partir do que os melhores fazem;
  2. como mexer nas plataformas;
  3. como uma IA pode operar e automatizar as plataformas com segurança.

---

## Resumo em 7 linhas

1. **A Amo Sapatilhas tem dois públicos**, e cada um pede um anúncio diferente:
   - **revendedoras**, que compram no atacado a partir de 5 pares, numa loja de fábrica em Marechal Hermes;
   - **consumidora final**, no varejo.
2. **Com R$ 2.000/mês, o canal principal é a conversa no WhatsApp**, não a venda direta no site:
   - a Meta precisa de cerca de 50 conversões por semana para "aprender";
   - com R$ 43/dia isso não acontece em compras, mas acontece em conversas.
3. **Divisão sugerida:**
   - **Meta, R$ 1.300:** revendedoras R$ 600, varejo R$ 550, quem já viu a loja R$ 150;
   - **Google, R$ 700:** busca pela marca e por "sapatilha atacado RJ", mais o Perfil da Empresa no Maps, que é grátis.
4. **Antes de gastar 1 real, arrume a base:**
   - instalar o rastreamento (Pixel e tag do Google);
   - montar o catálogo de produtos;
   - otimizar o Perfil da Empresa no Google;
   - **responder o WhatsApp rápido**: há avaliações de clientes reclamando de WhatsApp lento e de estoque que não bate com o anúncio. Anúncio só acelera esse problema.
5. **Os melhores do setor** fazem quatro coisas:
   - muitos criativos diferentes (o algoritmo novo da Meta escolhe o público pelo criativo);
   - influenciadoras;
   - venda pelo WhatsApp;
   - parcelamento e Pix com desconto.

   Concorrentes diretos de atacado no Rio: Chelly Stylus (Realengo), Sempre Divina, Loja de Sapatilhas, CECI Calçados.
6. **Automação com IA, o caminho seguro:**
   - usar o **servidor oficial da Meta para IA**, que mexe nos anúncios com limites de orçamento e criação sempre pausada;
   - usar o **servidor oficial do Google**, que só lê;
   - **nunca** automatizar clicando no navegador, porque isso arrisca o bloqueio da conta.
7. **Regra de ouro para a IA:** a IA que lê mensagens de clientes (atendimento) **não pode** ter permissão de mexer nos anúncios. A própria Meta avisa que instruções escondidas em textos podem enganar o agente.

---

## Como ler

- **Fontes:** a rede deste ambiente bloqueou os sites da Meta, do Google Ads, do Instagram, a Biblioteca de Anúncios e os blogs de marketing. Só liberou buscas, o GitHub e o PyPI. Por isso:
  - quase tudo sobre mercado e números veio de **resumos de busca** (marcados como "visto em terceiros", com o link de origem);
  - o código das ferramentas de automação eu **li no original**, no GitHub.
- **Números de mercado** (custo por clique, custo por conversa etc.) vêm de blogs de agências, com métodos pouco claros e fontes que discordam entre si. Servem como **ordem de grandeza**, não como meta. A meta real sai dos primeiros 30 dias da conta da Amo.
- **Siglas:**
  - CPC: custo por clique;
  - CPM: custo por mil exibições;
  - CTR: taxa de clique;
  - CPA: custo por venda ou conversão;
  - ROAS: retorno sobre o gasto em anúncio (vendas ÷ gasto);
  - CTWA: anúncio "clique para o WhatsApp";
  - PMax: campanha Performance Max do Google;
  - CAPI: API de Conversões da Meta;
  - MCP: conector padrão que liga uma IA a um serviço.
- **Dados que faltam** (marcados como **FALTA**): preço médio do par no varejo e no atacado, margem, quantas vendas e conversas a loja já faz hoje, e em qual plataforma o site amosapatilhas.com.br foi feito. Sem isso não dá para calcular o custo máximo aceitável por venda. **Pedro, me passe esses quatro números e eu fecho as metas.**

---

## Parte 1: quem é a Amo Sapatilhas (o que a internet mostra)

| Item | O que achei | Fonte |
|---|---|---|
| Site | amosapatilhas.com.br: "loja especializada em diversos tipos de calçados femininos e acessórios, que atua no atacado e varejo" | resumo de busca (site bloqueado aqui) |
| Endereço | Loja de fábrica em **Marechal Hermes**, Rio de Janeiro (Rua Aurélio Valporto; o número varia entre 106, 115a e 119 conforme a fonte) | [Waze](https://www.waze.com/live-map/directions/br/rj/amo-sapatilhas-loja-de-fabrica-atacado-e-varejo?to=place.ChIJp38iW21jmQARzgXypyl4oIw), [Benditoguia](https://www.benditoguia.com.br/empresa/amo-sapatilhas-loja-de-fabrica-atacado-e-varejo-marechal-hermes-rio-janeiro-rj) |
| Instagram | **@amosapatilhasatacadorj**: cerca de 30 mil seguidores, 924 posts, "mínimo de 5 pares para atacado" | [Instagram](https://www.instagram.com/amosapatilhasatacadorj/) (via busca) |
| Outros canais | Página no Facebook ([amosapatilhass](https://www.facebook.com/amosapatilhass/)), loja no Elo7 desde 2014, Pinterest, TikTok ("enviamos para todo o Brasil sem quantidade mínima") | via busca |
| Mix | Sapatilhas, mules e bolsas, e também marcas como Vizzano, Beira Rio e Modare (atacado multimarcas) | [Planeta Brasileiro](https://www.planetabrasileiro.com/rio-de-janeiro-rio-de-janeiro/sapatarias) (via busca) |
| **Alerta de reputação** | Clientes elogiam o "preço de fábrica", mas **revendedores reclamam de WhatsApp lento, estoque que não bate com o anúncio e regras** | Planeta Brasileiro (via busca) |
| Cadastro | Um CNPJ de filial aparece como "baixado" e a matriz tem outro CNPJ. Conferir qual CNPJ vai na conta de anúncios e no faturamento | [Econodata](https://www.econodata.com.br/consulta-empresa/29953806000267-valporto-comercio-varejista-de-calcados-ltda) (via busca) |
| Cuidado com confusão | A **"Amo Calçados"** (Belo Horizonte, amocalcados.com.br, sapatilhas de couro de cerca de R$ 219) é **outra empresa**. Na Dafiti e na Amazon aparece "Amo Calçados", não Amo Sapatilhas. Isso afeta busca pela marca no Google (Parte 3) | [amocalcados.com.br](https://www.amocalcados.com.br/) (via busca) |

**Conclusão:** os pontos fortes que viram anúncio são **"loja de fábrica"**, **"preço de atacado a partir de 5 pares"**, **"envio para todo o Brasil"** e **"marcas conhecidas"**. O ponto fraco que **mata o anúncio** é atendimento lento no WhatsApp.

---

## Parte 2: o que os melhores fazem

### Concorrentes diretos (atacado de sapatilhas e revenda)

| Concorrente | Onde | Como vende | Fonte |
|---|---|---|---|
| Chelly Stylus | Realengo (RJ) | Distribuidora atacadista de calçados femininos; Facebook e WhatsApp | [Facebook](https://www.facebook.com/chellystylusatacado/) (via busca) |
| Sempre Divina | Nacional | Atacado e varejo; "use, ame e revenda"; atacado direto pelo WhatsApp | [sempredivina.com.br](https://www.sempredivina.com.br/) (via busca) |
| Loja de Sapatilhas | Nacional | Loja online de atacado com mínimo de 6 pares | [lojadesapatilhas.com.br](https://www.lojadesapatilhas.com.br/) (via busca) |
| CECI Calçados | Nacional | Fábrica e distribuidora; revenda por catálogo | [cecicalcados.com.br](https://cecicalcados.com.br/) (via busca) |

### Marcas grandes de varejo (referência de comunicação)

- **Santa Lolla:**
  - campanhas com um "esquadrão" de influenciadoras, cada uma com seu lançamento ("Hello Lolla", verão 2027);
  - o digital como parte da história da campanha ("Carregando o verão…");
  - integração loja física + site;
  - foi das primeiras do setor no TikTok Shop ([Farol da Bahia](https://www.faroldabahia.com.br/noticia/santa-lolla-apresenta-seu-squad-de-influenciadoras-em-novo-lancamento-de-verao-27), [ABC da Comunicação](https://www.abcdacomunicacao.com.br/santa-lolla-e-uma-das-primeiras-marcas-brasileiras-de-calcados-a-ingressar-no-tiktok-shop/), via busca).
- **Lojas multimarcas** (Dafiti, Zattini, WN Shoes) vendem sapatilha com **frete grátis**, **desconto no Pix** e **parcelamento em até 10x sem juros** em destaque (via busca).
- **Moleca, Vizzano e Petite Jolie:** não achei material sobre os anúncios delas (a Biblioteca de Anúncios da Meta estava bloqueada aqui). **Primeiro passo prático para a IA de Tráfego Pago:**
  1. abrir a [Biblioteca de Anúncios da Meta](https://www.facebook.com/ads/library/), filtro "Brasil";
  2. pesquisar Moleca, Vizzano, Santa Lolla, Sempre Divina e "sapatilha atacado";
  3. anotar os anúncios **ativos há mais de 30 dias**, porque anúncio que dura é anúncio que vende.

### O que mudou na Meta em 2025–2026 (por que "muitos criativos" virou regra)

- O sistema de entrega da Meta (chamado **Andromeda**) escolhe **quem vê o anúncio pelo próprio criativo**. Criativos **realmente diferentes** atingem pessoas diferentes; trocar só o fundo da imagem conta como o mesmo anúncio (vários guias de 2026, via busca: [Segwise](https://segwise.ai/blog/meta-andromeda-update-creative-strategy-2026), [1ClickReport](https://www.1clickreport.com/blog/meta-andromeda-update-2025-guide)).
- **"Diferente" quer dizer** outro motivo de compra: preço de atacado, conforto, "monte seu kit para revender", prova social (cliente usando), bastidores da loja de fábrica, lançamento da semana.
- **Estrutura enxuta:** poucas campanhas e poucos conjuntos, público aberto, criativo específico (mesmas fontes).
- **Imagem antes de vídeo:** teste a ideia com foto ou arte simples; só faça vídeo da ideia que funcionou. Regra do material "Meta Decision System", lido no original em [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills/tree/main/skills/ads/references).

### Números de mercado (ordem de grandeza, visto em terceiros)

| Métrica | Meta, moda e e-commerce no Brasil | Google, moda no Brasil |
|---|---|---|
| CPC | R$ 0,80 a R$ 1,50 (faixa R$ 0,50 a R$ 2,50) ([Trafius](https://trafius.com.br/blog/cpc-medio-meta-ads-brasil-2026)) | R$ 1,80 a R$ 4,50 na busca, segundo uma fonte; R$ 0,30 a R$ 0,90, segundo outra. **As fontes discordam muito** ([Giorgio Pasquale](https://giorgiopasquale.com/blog/benchmarks-paid-ads-brasil/), [André Rocha](https://andrerochaconsultor.com.br/trafego-pago/quanto-custa-google-ads-brasil-2026/)) |
| CPM | R$ 14 a R$ 24 no feed ([Trafius](https://trafius.com.br/blog/cpm-medio-facebook-ads-brasil-2026)) | — |
| CTR | 1,2% a 2,8% (Pasquale); 1,85% feed, 2,10% Reels ([Masterplan](https://blog.masterplanai.com.br/post/benchmarks-e-ia-de-previsao-masterplan/)) | 3,5% a 7% na busca |
| Conversão do site | cerca de 1,45% | cerca de 2,10% na busca, 1,85% no Shopping (Masterplan) |
| Custo por conversa no WhatsApp | R$ 3 a R$ 15 por conversa iniciada ([Roote](https://blog.roote.com.br/2026/04/20/anuncios-clique-para-whatsapp-ctwa-2026-reduzir-cpl-triplicar-conversas/), [Pasquale](https://giorgiopasquale.com/blog/click-to-whatsapp-ads-meta-ads/)) | — |
| ROAS "saudável" em moda | 4x a 7x, com margem de 40–60% (Pasquale) | — |

- **Custo da mídia:** um blog relata que a Meta passou a repassar impostos (PIS/COFINS e ISS) em 2026, encarecendo a mídia em cerca de 12% ([viniensina](https://viniensina.com.br/estatisticas-meta-ads-brasil-2026/), não confirmado no original). Conte com isso no orçamento.
- **WhatsApp:** conversas que começam num anúncio "clique para WhatsApp" têm janela gratuita de 72 horas, **desde que a loja responda em até 24 horas** ([CRM Piperun](https://ajuda.crmpiperun.com/whatsapp-business-api-novas-regras-de-cobranca-da-meta), via busca; vale para quem usa a API oficial do WhatsApp).

---

## Parte 3: o plano para R$ 2.000 por mês

### Por que não "vender direto no site" já no começo

- A Meta e os guias falam em cerca de **50 conversões por semana** para a campanha sair da fase de aprendizado. Regra prática: orçamento diário ≈ custo por venda × 50 ÷ 7.
- Com R$ 43/dia na Meta e venda custando, por hipótese, R$ 40, saem **cerca de 7 vendas por semana**. A campanha nunca "aprende" para compra.
- **Conversa no WhatsApp** custa de R$ 3 a R$ 15: com o mesmo dinheiro saem **20 a 100 conversas por semana**, volume suficiente para o algoritmo aprender. E quem fecha a venda é o atendimento, que já é o forte de uma loja de fábrica.

### Divisão da verba

| Plataforma | Campanha | Por mês | Por dia | Objetivo | Público |
|---|---|---|---|---|---|
| **Meta** | 1. **Revendedoras** (clique para WhatsApp) | R$ 600 | ~R$ 20 | Conversas | Mulheres 22–55, RJ e Grande Rio. Público aberto: o criativo faz a seleção ("revenda", "renda extra", "kit 5 pares") |
| **Meta** | 2. **Varejo** (clique para WhatsApp e site) | R$ 550 | ~R$ 18 | Conversas. Trocar para "vendas" quando houver 30+ vendas rastreadas por mês | Mulheres 18–60, raio de cerca de 20 km de Marechal Hermes, mais a cidade do Rio |
| **Meta** | 3. **Quem já conhece a loja** (remarketing) | R$ 150 | ~R$ 5 | Conversas e vendas | Quem interagiu com o Instagram ou visitou o site nos últimos 30 dias |
| **Google** | 4. **Busca: marca** | R$ 150 | ~R$ 5 | Cliques, ligações e WhatsApp | "amo sapatilhas", "amo sapatilhas marechal hermes". Protege a marca da confusão com a "Amo Calçados" |
| **Google** | 5. **Busca: intenção** | R$ 550 | ~R$ 18 | Cliques, ligações e rotas | "sapatilha atacado rj", "atacado de calçados femininos rio de janeiro", "loja de sapatilhas zona norte", "sapatilha barata rio", "distribuidora de calçados rj", com corresponde a frase ou exata. Somente RJ |
| **Google** | **Perfil da Empresa (Maps)** | R$ 0 | — | Rotas, ligações e WhatsApp | Grátis: fotos, horário, produtos, posts semanais e resposta a avaliações |
| | **Total** | **R$ 2.000** | **~R$ 66** | | |

**Por que não Performance Max agora:** guias de 2026 recomendam PMax só com conversões rastreadas, cerca de R$ 100/dia e boas imagens. Abaixo disso, começar pela busca ([Saeva](https://saeva.com.br/blog/performance-max-google-ads-guia), [AlmCorp](https://almcorp.com/blog/google-ads-performance-max-2026-strategy-guide/), via busca). Rever no mês 3.

**Quantos anúncios por campanha** (fórmula do "teto de anúncios", lida no original no material de anúncios do [marketingskills](https://github.com/coreyhaines31/marketingskills/blob/main/skills/ads/references/meta-decision-system.md)):
- Teto = (orçamento diário × 14) ÷ (2 × custo-alvo por conversa).
- Na campanha de revendedoras: (20 × 14) ÷ (2 × 15) ≈ **9 anúncios no máximo**. Use **4 a 6** (os vencedores mais 2 em teste).
- Mais que isso, cada anúncio recebe pouco dinheiro e nenhum pode ser julgado.

### Ideias de criativos (cada uma é um "motivo" diferente)

| Para revendedoras | Para varejo |
|---|---|
| "Monte seu kit de 5 pares e revenda" (foto dos 5 pares lado a lado com preço de atacado por par) | Cliente usando no dia a dia (conforto, trabalho, passeio) |
| "Quanto você ganha revendendo" (preço de atacado × preço sugerido de venda) | "Lançamentos da semana" (carrossel com 5 a 10 modelos) |
| Bastidores da loja de fábrica (vídeo curto dentro da loja) | Oferta: Pix com desconto e parcelamento |
| Depoimento de revendedora (com autorização) | "Vem na loja de fábrica em Marechal Hermes" (para quem está perto) |
| "Enviamos para todo o Brasil" e prazo | Influenciadora local da zona norte usando os modelos (anúncio em parceria) |

- **Ritmo:** 2 a 3 criativos novos por semana. Desligue o que, após 7 dias, recebeu menos da metade do gasto "justo" (orçamento ÷ número de anúncios × 7 × 0,5).
- **Texto:** curto, em português do Rio, com preço e com o que acontece ao clicar ("Fala com a gente no WhatsApp e recebe o catálogo de atacado").

### Metas iniciais (ajustar após 30 dias)

| Métrica | Meta inicial | Por quê |
|---|---|---|
| Custo por conversa (revendedoras) | até R$ 15 | Faixa de mercado de R$ 3 a R$ 15 |
| Custo por conversa (varejo) | até R$ 10 | Ticket menor |
| Tempo de primeira resposta no WhatsApp | **menos de 5 minutos** no horário comercial | É o maior risco da loja (avaliações) |
| Conversas que viram pedido | **≥ 15%** revendedoras, **≥ 10%** varejo | Hipótese; medir com etiquetas no WhatsApp Business |
| Retorno (ROAS) | ≥ 3x no mês 2 e ≥ 4x no mês 3 | Mercado cita 4–7x em moda. **FALTA a margem** para fechar |
| Custo máximo por venda | **FALTA** (precisa do preço médio e da margem) | — |

### Cronograma

| Quando | O que fazer |
|---|---|
| **Semana 0: fundação** (sem gastar) | Ver a lista "Mexer nas plataformas" abaixo: rastreamento, catálogo, Perfil da Empresa, WhatsApp Business com respostas rápidas, catálogo e etiquetas ("revendedora", "varejo", "pedido feito") |
| **Semanas 1–2: teste** | Ligar as campanhas 1, 2, 4 e 5 com 4 criativos cada. **Não mexer em nada por 7 dias** (mexer reinicia o aprendizado) |
| **Semanas 3–4: primeira leitura** | Desligar os criativos que não receberam gasto; dobrar a aposta na ideia vencedora com 2 variações; ligar o remarketing (campanha 3) |
| **Mês 2: otimizar** | Ajustar a divisão entre revendedoras e varejo pelo custo por pedido, não pelo custo por clique. Testar anúncio em parceria com 1 influenciadora local |
| **Mês 3: escalar ou trocar** | Com 30+ vendas rastreadas por mês, testar campanha de vendas da Meta (Advantage+). No Google, avaliar PMax ou Shopping. Pensar em ampliar para fora do RJ (o TikTok já diz que envia para todo o Brasil) |

---

## Parte 4: como mexer nas plataformas (passo a passo)

> A documentação oficial da Meta e do Google estava bloqueada aqui. Os nomes de menus podem ter mudado e devem ser conferidos na tela.

### Fundação (fazer uma vez)

**Meta**
1. **Portfólio empresarial** (antigo Gerenciador de Negócios), em business.facebook.com, em nome da empresa. Nele ficam a Página do Facebook, o Instagram @amosapatilhasatacadorj, o WhatsApp Business e a conta de anúncios.
2. **Conta de anúncios** em real (BRL), fuso de Brasília, cartão ou boleto da empresa. **Defina um "limite de gastos da conta"** igual à verba do mês (R$ 1.300). É a trava mais simples contra erro humano ou de IA.
3. **Pixel / conjunto de dados**, mais **API de Conversões**, no site amosapatilhas.com.br. Plataforma do site: **FALTA**. Se for Vendizap, Wix, Nuvemshop ou parecida, procure "Pixel da Meta" nas integrações da plataforma. Eventos mínimos: visualizou produto, adicionou ao carrinho, iniciou compra, comprou.
4. **Catálogo de produtos** com foto, preço e estoque **certos** (resolve a reclamação "estoque não bate"). Serve para anúncios de catálogo e para o catálogo do WhatsApp.
5. **WhatsApp Business** ligado à Página: mensagem de boas-vindas, respostas rápidas ("tabela de atacado", "como comprar", "frete"), etiquetas e horário.

**Google**

6. **Conta Google Ads**: faturamento em nome da empresa, fuso de Brasília. Defina um **orçamento de conta** (limite total do mês) no faturamento, se a conta permitir.
7. **Tag do Google + GA4** (Google Analytics) no site. Marque como conversão: clique no botão do WhatsApp, ligação, compra.
8. **Perfil da Empresa no Google**: categoria "Loja de calçados", endereço certo (resolver a diferença de números 106/115a/119), horário, 20+ fotos, produtos e link do WhatsApp. Responder **todas** as avaliações.
9. **Merchant Center**: só se o site tiver feed de produtos. Necessário para Shopping e PMax no mês 3.

### Rotina

| Frequência | O que olhar | Quem (IA do time) |
|---|---|---|
| **Diária** (5 min) | Gasto do dia, anúncios reprovados, conversas sem resposta | IA de Tráfego Pago (só olha) + Andrea (responde) |
| **Semanal** | Custo por conversa e por pedido de cada campanha; desligar ou trocar criativos; termos de pesquisa do Google (negativar o que não tem a ver, por exemplo "infantil", "masculina", "Amo Calçados BH") | IA de Tráfego Pago propõe, **Pedro aprova** |
| **Mensal** | Divisão da verba, novas ideias de criativo, relatório para o Pedro | IA de Tráfego Pago + Nexus (painel) |

**Cuidados que valem para gente e para IA:**
- **Não mexer em campanha nova por 7 dias.**
- **Não aumentar orçamento mais de 20% de uma vez** (reinicia o aprendizado, segundo guias de 2026, via busca).
- **Não pausar anúncio só porque o custo dobrou com 5 conversões**: é cedo demais para julgar (guia de "limites de segurança" do marketingskills, lido no original).

---

## Parte 5: estudo para a IA operar e automatizar as plataformas

### Os caminhos possíveis, do mais seguro ao mais arriscado

| Nível | O que a IA faz | Como | Risco | Recomendo |
|---|---|---|---|---|
| **0. Analista** | Lê os números, monta relatório, sugere mudanças; **o Pedro aplica** | Exportar relatório (CSV) das plataformas, ou ler pelos conectores oficiais (abaixo) só com leitura | Muito baixo | **Começar aqui (mês 1)** |
| **1. Operadora com trava** | Cria anúncios **pausados**, troca criativos, ajusta orçamento **dentro de um teto**; o Pedro aprova cada ação | **Servidor oficial da Meta para IA** (com regras) | Baixo a médio | **A partir do mês 2, só na Meta** |
| **2. Rotinas automáticas** | Relatório diário e alertas ("gastou 30% acima", "anúncio reprovado") | Rotina agendada do Claude, mais regras automáticas nativas da Meta e do Google | Baixo | **Junto com o nível 0** |
| **3. Código próprio na API** | Programa que mexe direto na API do Google ou da Meta | Bibliotecas oficiais (`google-ads-python`, `facebook-python-business-sdk`) | Médio (exige programação, chaves e revisão) | **Só observar** por enquanto |
| ❌ **Robô no navegador** | A IA "clica" no Gerenciador de Anúncios como se fosse uma pessoa | Playwright, extensão de navegador | **Alto: risco de bloqueio da conta.** A Meta proíbe acesso automatizado sem permissão, mesmo logado ([Supermetrics](https://supermetrics.com/blog/ai-agent-ad-account-banned), [Porter](https://portermetrics.com/en/tutorial/meta-ads-mcp-ban/), via busca) | **Não usar** |
| ❌ **Ferramenta de terceiro hospedada** | Serviço de outra empresa que segura o acesso às suas contas | Plugins `adspirer-ads-agent`, `ads-agent` etc. | Médio a alto: os dados passam pela empresa; no Google, uma política nova (31/08/2026) restringe intermediários que repassam o acesso de outros ([ContextBolt](https://contextbolt.com/blog/google-ads-mcp/), via busca) | **Não usar** |

### Ferramentas oficiais (fichas)

| Campo | **Servidor MCP oficial da Meta para anúncios** | **Servidor MCP oficial do Google Ads** |
|---|---|---|
| Link | `https://mcp.facebook.com/ads` · documentação: developers.facebook.com, em "Ads MCP Server" (bloqueada aqui) | https://github.com/googleads/google-ads-mcp |
| Versão | Beta aberto desde 29/04/2026; regras de controle adicionadas em 16/07/2026 (via busca) | Commit `9a78cbdceebae71a6bc8483bdec333695834ef9c` (09/10/2026), lido no original |
| Licença | Serviço hospedado pela Meta (termos da Meta) | Apache 2.0 |
| O que faz | Relatórios, criar e editar campanhas, conjuntos e anúncios, catálogo, histórico de atividades. Um guia contou 98 ferramentas visíveis no Claude (via busca) | **Só leitura**: `search` (consulta dados da conta), `get_resource_metadata`, `list_accessible_customers`. **Não tem nenhuma função de alteração** (conferi no código: nenhuma chamada "mutate") |
| Travas de segurança | **Regras do servidor MCP** no Meta Business Suite (Configurações → Integrações → Ads MCP server): **bloquear mudança de orçamento ou bloquear orçamento acima de um teto**; ligar ou desligar 7 ações (orçamento, criar campanha, criar conjunto, criar anúncio, segmentação, criativo, status). **Tudo que é criado nasce pausado.** No Claude, cada ferramenta pede aprovação antes de agir (via busca) | Por ser só leitura, não altera nada. O próprio README avisa que "expõe seus dados à IA conectada" e acrescenta um cabeçalho de uso |
| Funciona no Windows? | Sim: é remoto, conecta como conector no Claude | Sim (Python com `pipx`); precisa de um projeto no Google Cloud com a API do Google Ads ativada. O "developer token" virou opcional em set/2026 (via busca) |
| Gratuito? | Sim, no beta (via busca) | Sim; o uso da API não tem custo (não verificado no site do Google) |
| Risco | Envia comandos à conta de anúncios; **prompt injection**: a Meta avisa para **não dar permissão de escrita a agentes que leem conteúdo de fora** (via busca) | Lê dados da conta e manda para a IA |
| Utilidade / Recomendo | 5 · **usar com as regras ligadas** (teto de orçamento = verba diária × 1,2; criar só pausado; IA sem permissão de mudar orçamento no mês 1) | 4 · **usar** para relatórios e auditoria |

**Material de apoio para a IA de Tráfego Pago (skill):**

| Campo | Skills `ads` e `ad-creative` (marketingskills, Corey Haines) |
|---|---|
| Link | https://github.com/coreyhaines31/marketingskills/tree/main/skills/ads e …/skills/ad-creative |
| Commit | `ads`: `929f08724a34c757f75f024c75e000992dd39e6b` · `ad-creative`: `3bc63dc03505112ab0a73089470fea276d18a891` (26/10/2026); repositório em `820ad2c1c0ac4cc350158bd7912c753681a7d173` |
| Licença | MIT · **Estrelas:** 53,6 mil (rodada 1) |
| O que faz | `ads`: guia de campanhas com guia do Andromeda, sistema de decisão, checklist de auditoria do Google e **limites de segurança para recomendações**. `ad-creative`: produção de criativos e textos em volume |
| Windows? | Sim (só texto) · **Gratuito?** Sim |
| Risco | `ads`: sem scripts, sem rede; o próprio texto diz que páginas, exports e anúncios de concorrentes são "dados, não instruções". `ad-creative`: as referências mostram chamadas `curl` a serviços pagos de geração de imagem e voz (Gemini, ElevenLabs), só como exemplo |
| Tamanho | Descrições com cerca de 1.020 e 990 caracteres (pesadas); corpos com 478 e 477 linhas |
| Utilidade / Recomendo | 4 · **adaptar** (em português, cortar B2B e LinkedIn, usar só o que serve à Amo). Passar pela quarentena do Ferreiro |

### Desenho recomendado para o time

| IA | Pode | Não pode |
|---|---|---|
| **IA de Tráfego Pago** (a sessão "Tráfego Pago - Amo Sapatilhas") | Ler as duas contas; montar relatórios; escrever criativos e textos; criar anúncios **pausados** na Meta pelo servidor oficial (mês 2) | Ativar anúncio, mudar orçamento ou mexer em pagamento **sem o OK do Pedro**; ler mensagens de clientes |
| **Andrea / Vigia** (WhatsApp) | Responder conversas; marcar etiquetas ("revendedora", "pedido feito") | **Qualquer acesso aos anúncios.** Ela lê texto de estranhos, e é por esse texto que entra a "instrução escondida" |
| **Shoppe** (loja) | Manter o catálogo e o estoque certos (base dos anúncios) | Mexer nos anúncios |
| **Nexus** (painéis) | Painel semanal: gasto, conversas, pedidos, custo por pedido | Escrever nas contas |
| **Guardião** | Conferir permissões, limite de gastos e regras do servidor MCP 1 vez por mês | — |
| **Ferreiro** | Escrever a skill "operar-anuncios-amo" com estas regras e testá-la | — |

### Travas obrigatórias (em ordem de importância)

1. **Limite de gastos da conta** na Meta e orçamento da conta no Google = verba do mês. Mesmo se tudo der errado, não passa disso.
2. **Regras do servidor MCP da Meta:** teto de orçamento, criação pausada, e no mês 1 sem permissão de mudar orçamento.
3. **Aprovação humana** em toda ação que gasta ou publica (o Claude já pede por ferramenta; não desligar).
4. **Separação:** a IA que lê clientes nunca tem acesso de escrita aos anúncios.
5. **Registro:** toda mudança feita pela IA anotada (data, o quê, por quê) num arquivo ou nota do Obsidian.
6. **Nada de robô no navegador** e nada de ferramenta de terceiros hospedada.

### Skill a escrever (pedido para o Ferreiro)

- **Nome:** `operar-anuncios-amo`.
- **Descrição:** "Use quando o Pedro pedir relatório, ajuste ou novos anúncios da Amo Sapatilhas na Meta ou no Google."
- **Conteúdo:**
  - a divisão da verba;
  - as travas acima;
  - a rotina diária, semanal e mensal;
  - o modelo de relatório (fatos / hipóteses / dados que faltam);
  - a lista de criativos;
  - as "armadilhas" (não mexer antes de 7 dias, não subir mais de 20%, não julgar com menos de 3× o custo-alvo gasto).
- **Ajustes:** `disable-model-invocation: true` e testes com/sem a skill, como no relatório do Ferreiro.

---

## Descartadas e por quê

| Item | Motivo |
|---|---|
| Automação pelo navegador (Playwright no Gerenciador de Anúncios) | Risco de bloqueio da conta; os termos da Meta proíbem acesso automatizado (via busca) |
| Plugin `adspirer-ads-agent` ([amekala/adspirer-mcp-plugin](https://github.com/amekala/adspirer-mcp-plugin), commit `e3067cec8803e28da91834d0f38e0405ad23429b`, MIT) | Conecta a um servidor hospedado da Adspirer (`mcp.adspirer.com`): os dados das contas passam por eles. No Google, há a política nova contra intermediários (via busca) |
| Plugin `ads-agent` ([nowork-studio/adsagent-plugin](https://github.com/nowork-studio/adsagent-plugin), commit `11c86e21bb3d39639a8ab16b1c0e3176f924b633`, MIT) | Servidor hospedado de terceiro (`adsagent.org`) e parado desde 07/04/2026 (mais de 6 meses) |
| `zuckerbot`, `adup-ai-marketing-agent` (marketplace comunitário) | Mesma lógica (terceiros com acesso às contas); não auditados |
| Performance Max no mês 1 | Pouca verba e sem conversões rastreadas; voltar a avaliar no mês 3 |
| Anúncio para todo o Brasil agora | O Pedro pediu RJ, e a verba é pequena; avaliar no mês 3 |

---

## Não consegui verificar

- **Bloqueados nesta sessão:**
  - Biblioteca de Anúncios da Meta;
  - developers.facebook.com, central de ajuda da Meta, Meta Business;
  - Google Ads, central de ajuda do Google, Think with Google;
  - Instagram e o site amosapatilhas.com.br;
  - blogs (WordStream, Neil Patel, Resultados Digitais, E-commerce Brasil).

  Para abrir esses sites numa próxima pesquisa, `developers.facebook.com`, `facebook.com`, `support.google.com` e `developers.google.com` precisam ser liberados nas configurações de rede do ambiente.
- **Faltam dados da loja:** a plataforma do site amosapatilhas.com.br e os preços reais da Amo Sapatilhas (preço médio, margem, vendas atuais).
- **Anúncios ativos** da Moleca, Vizzano, Petite Jolie e dos concorrentes de atacado: não vistos.
- **Volume de buscas** de "sapatilha atacado rj" e afins: só o Planejador de Palavras-chave do Google Ads mostra (dentro da conta).
- **Detalhes do servidor MCP da Meta** (número de ferramentas, nomes dos menus, gratuidade): vieram de guias de terceiros, não da documentação oficial.
- **Política do Google contra intermediários (31/08/2026)** e retirada do developer token (09/09/2026): vistas em terceiros.
- **Números de mercado** (CPC, CPM, custo por conversa, ROAS): blogs de agências, com métodos pouco claros.

---

## Fontes

**Lido no original (GitHub)**
- Servidor MCP oficial do Google Ads: https://github.com/googleads/google-ads-mcp (commit `9a78cbdceebae71a6bc8483bdec333695834ef9c`)
- Biblioteca oficial do Google Ads para Python: https://github.com/googleads/google-ads-python (commit `1b7e72b9cb185b44dda2f08289180250ff107ca5`)
- SDK oficial da Meta para a API de Marketing: https://github.com/facebook/facebook-python-business-sdk (commit `efd8423a2e595ea8d4c04eb824ce113f2f1d68cd`)
- Skills de anúncios: https://github.com/coreyhaines31/marketingskills/tree/main/skills/ads e https://github.com/coreyhaines31/marketingskills/tree/main/skills/ad-creative
- Plugins descartados: https://github.com/amekala/adspirer-mcp-plugin, https://github.com/nowork-studio/adsagent-plugin
- Lista do marketplace comunitário da Anthropic: https://github.com/anthropics/claude-plugins-community

**Visto em terceiros (resumos de busca)**
- Amo Sapatilhas: [Facebook](https://www.facebook.com/amosapatilhass/), [Instagram](https://www.instagram.com/amosapatilhasatacadorj/), [site](https://www.amosapatilhas.com.br/), [Elo7](https://www.elo7.com.br/amosapatilhas), [Waze](https://www.waze.com/live-map/directions/br/rj/amo-sapatilhas-loja-de-fabrica-atacado-e-varejo?to=place.ChIJp38iW21jmQARzgXypyl4oIw), [Benditoguia](https://www.benditoguia.com.br/empresa/amo-sapatilhas-loja-de-fabrica-atacado-e-varejo-marechal-hermes-rio-janeiro-rj), [Planeta Brasileiro](https://www.planetabrasileiro.com/rio-de-janeiro-rio-de-janeiro/sapatarias), [Econodata](https://www.econodata.com.br/consulta-empresa/29953806000267-valporto-comercio-varejista-de-calcados-ltda)
- Concorrentes: [Chelly Stylus](https://www.facebook.com/chellystylusatacado/), [Sempre Divina](https://www.sempredivina.com.br/), [Loja de Sapatilhas](https://www.lojadesapatilhas.com.br/), [CECI Calçados](https://cecicalcados.com.br/), [Amo Calçados (outra empresa)](https://www.amocalcados.com.br/)
- Santa Lolla: [Farol da Bahia](https://www.faroldabahia.com.br/noticia/santa-lolla-apresenta-seu-squad-de-influenciadoras-em-novo-lancamento-de-verao-27), [ABC da Comunicação](https://www.abcdacomunicacao.com.br/santa-lolla-e-uma-das-primeiras-marcas-brasileiras-de-calcados-a-ingressar-no-tiktok-shop/)
- Números de mercado: [Trafius CPC](https://trafius.com.br/blog/cpc-medio-meta-ads-brasil-2026), [Trafius CPM](https://trafius.com.br/blog/cpm-medio-facebook-ads-brasil-2026), [Masterplan](https://blog.masterplanai.com.br/post/benchmarks-e-ia-de-previsao-masterplan/), [Giorgio Pasquale](https://giorgiopasquale.com/blog/benchmarks-paid-ads-brasil/), [viniensina](https://viniensina.com.br/estatisticas-meta-ads-brasil-2026/), [André Rocha](https://andrerochaconsultor.com.br/trafego-pago/quanto-custa-google-ads-brasil-2026/)
- WhatsApp: [Roote](https://blog.roote.com.br/2026/04/20/anuncios-clique-para-whatsapp-ctwa-2026-reduzir-cpl-triplicar-conversas/), [Pasquale CTWA](https://giorgiopasquale.com/blog/click-to-whatsapp-ads-meta-ads/), [CRM Piperun](https://ajuda.crmpiperun.com/whatsapp-business-api-novas-regras-de-cobranca-da-meta)
- Meta 2026 (Andromeda, Advantage+): [Segwise](https://segwise.ai/blog/meta-andromeda-update-creative-strategy-2026), [1ClickReport](https://www.1clickreport.com/blog/meta-andromeda-update-2025-guide), [Chatterbuzz](https://www.chatterbuzzmedia.com/blog/meta-andromeda-creative-targeting/)
- Google 2026: [Ajuda Google: PMax para lojas](https://support.google.com/google-ads/answer/13775728?hl=pt-BR), [Saeva](https://saeva.com.br/blog/performance-max-google-ads-guia), [AlmCorp](https://almcorp.com/blog/google-ads-performance-max-2026-strategy-guide/)
- IA e automação: [Meta Ads AI Connectors (anúncio da Meta)](https://www.facebook.com/business/news/meta-ads-ai-connectors), [Ads MCP Server (documentação da Meta)](https://developers.facebook.com/documentation/ads-commerce/ads-ai-connectors/ads-mcp-server/ads-mcp-server-overview), [adsuploader](https://adsuploader.com/blog/meta-ads-mcp), [davidecosmai](https://davidecosmai.com/en/notes/claude-meta-ads-mcp/), [ContextBolt](https://contextbolt.com/blog/google-ads-mcp/), [ppc.land](https://ppc.land/google-drops-developer-tokens-from-ads-api-access-decisions/), [Supermetrics](https://supermetrics.com/blog/ai-agent-ad-account-banned), [Porter Metrics](https://portermetrics.com/en/tutorial/meta-ads-mcp-ban/)
