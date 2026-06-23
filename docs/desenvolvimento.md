# A Moça e o Pássaro — Processo de Desenvolvimento

*Documento de design e registro de desenvolvimento. Cobre o caminho do conceito original até a versão 2, com ênfase na decisão de design que reorganizou o projeto inteiro.*

---

## O conceito original

A ideia nasceu numa conversa anterior, ainda em voz alta: uma mulher encontra um pássaro filhote, cria-o, dá-lhe o melhor de tudo. Quando o pássaro cresce e aprende a voar, ela tem medo de que ele vá embora e não volte. Daí saem três caminhos. No bom, ela o deixa livre e ele volta de vez em quando — porque gostou do que ela fez por ele. No neutro, ele arrebenta a gaiola e some, sem voltar. No pior, ela corta as asas para impedi-lo de voar, e ele morre.

O requisito de forma era modesto e claro: algo de ler no celular, em qualquer lugar; texto puro no rascunho; um arquivo HTML simples de mandar para os amigos.

Há um detalhe nesse conceito que, lido com atenção, define o jogo todo: **no final bom, o pássaro volta porque gostou do cuidado.** Ou seja, o mesmo cuidado que faz o pássaro voltar é o que, administrado com medo, vira gaiola. Cuidado é simultaneamente o motor do retorno e o álibi do controle. Essa ambivalência é o coração da fábula — e foi exatamente o que a primeira versão não capturou.

---

## Primeira versão (v1)

A v1 entregou o que o conceito pedia ao pé da letra: 9 cenas, 3 finais, bilíngue (PT/EN com toggle), ilustrações em SVG embutidas, um arquivo único offline de 30 KB. Funcionava. Era bonita. E estava errada onde mais importava.

O problema não era técnico, era estrutural. As escolhas operavam como um roteador — "gaiola ou céu?" — com a resposta moralmente correta visível de longe. O jogador não *vivia um medo*; ele *escolhia um final*. Quem pegava a tesoura na v1 o fazia por curiosidade de completar a coleção de finais, não por tragédia. E uma fábula sobre amor possessivo que não consegue tornar a posse tentadora não está dizendo nada — está só rotulando emoções que o leitor deveria sentir.

A v1 ficou preservada, intacta, como ponto de comparação. A v2 foi reescrita do zero, reaproveitando apenas a identidade visual (paleta de crepúsculo, tipografia serifada) e o motor de troca de cenas.

---

## O diagnóstico

A tese que reorganizou o projeto cabe em uma frase: **o jogador nunca deve escolher "prender" — deve escolher "proteger".**

Cada passo em direção à gaiola precisa parecer razoável, quase carinhoso, no instante em que é dado. Fechar a janela numa noite de tempestade não é crueldade; é cuidado. Não deixar o pássaro sozinho quando um gato aparece no muro não é controle; é zelo. O horror não está em nenhuma escolha isolada — está na soma. É retrospectivo: a pessoa chega ao fim, olha para trás e percebe que engaiolou o pássaro por amor, uma decisão sensata de cada vez. Para isso funcionar, a gaiola tem que ser sedutora, e o caminho até ela tem que ser pavimentado de boas intenções.

Disso decorre o princípio de método que guiou toda a escrita: **emoção em ficção interativa se demonstra pela estrutura da escolha, não pelo adjetivo.** Não se escreve "ela sentiu medo"; constrói-se uma escolha cuja própria forma é o medo. O resto do design é a aplicação repetida dessa regra.

---

## As quatro mecânicas

### 1. O aperto

Um contador invisível de medo. O segundo ato deixa de ser uma bifurcação única e vira três batidas pequenas, cada uma oferecendo confiança ou aperto: a primeira ida do pássaro à janela, uma noite de tempestade ("fechar a janela — só esta noite"), um gato no muro somado ao comentário da vizinha. O contador não tranca finais — na cena da janela o jogador continua dono da decisão — mas tinge a narração. Com aperto alto, a gaiola chega quase inevitável: "ela já tinha comprado a gaiola na semana do gato, só por garantia — nem se lembrava de ter decidido comprá-la." E foi o jogador quem tornou isso verdade, sem nunca ter clicado em "comprar gaiola".

### 2. Os ecos

Escolhas do primeiro ato voltam, citadas, nos momentos finais. Quem fecha a janela na tempestade ouve, cenas depois, a própria frase de volta: "só esta noite, você disse — as janelas aprendem rápido." Quem escolheu alimentar o pássaro na palma da mão carrega nos finais agridoces uma dúvida a mais: *será que ele sabe procurar comida sozinho?* — porque foi essa a escolha que tirou dele o aprendizado. Culpa não se descreve; cobra-se. Nada acusa mais do que ser confrontado com as próprias palavras.

### 3. As confissões

Antes de cada final, uma escolha que não muda a rota — muda só a última linha. É espelho, não roteador. Na tesoura, as duas opções de corte *são* a confissão: "é para protegê-lo" / "ele é meu". O jogador articula o próprio motivo, e o jogo o devolve no epitáfio. A mesma morte ganha duas leituras conforme a razão que o jogador assume para ela.

### 4. Impotência e dupla confirmação

Impotência se demonstra tirando opções. A cena da espera tem um único botão — "esperar" —, e essa ausência de escolha diz "você não manda mais aqui" melhor que qualquer parágrafo. Já o final trágico não pode ser tropeço: precisa de assinatura. O rótulo visível é inocente ("abrir a gaveta da tesoura"); só dentro da cena aparece o corte, e mesmo ali existe uma saída real — "soltar a tesoura" — que devolve o jogador à decisão anterior, com a mão tremendo do que quase foi. Quem chega ao fim trágico escolheu chegar.

### A espera com tentação (a peça central)

No caminho da liberdade, depois de soltar o pássaro, vem a espera. No quarto dia de silêncio, surge a opção de desistir: "fechar a janela. Chega." Se o jogador cede, o pássaro volta na manhã seguinte — e encontra vidro. É o final mais cruel do jogo, porque a perda não vem da soltura; vem de um único momento de fraqueza *depois* do ato corajoso. O final feliz, com isso, deixa de ser um clique e passa a exigir confiar duas vezes. E o agridoce ganha três texturas da mesma perda: a fuga (ele arrebenta os arames sozinho, como no conceito original), a porta aberta tarde demais, e a janela fechada num dia de fraqueza.

---

## Como cada emoção virou estrutura

A tradução de sentimento em mecânica foi o trabalho de fundo. Vale registrar o mapeamento, porque ele é o que distingue este projeto de um simples "escolha sua aventura":

- **Ternura** — escolhas sem resposta errada no primeiro ato, escritas no registro sensorial (o peso na palma, o mamão maduro). Além de estabelecer o vínculo, isso ensina o jogador, sem aviso, de que aqui escolha é expressão de quem você é, não cálculo de estratégia.
- **Medo razoável** — as ameaças são reais (tempestade, gato), e há uma assimetria deliberada na redação: as opções de controle são sempre concretas e imediatas ("fechar a janela"), as de confiança são abstratas e assustadoras ("deixar que ele olhe"). Assim funciona a ansiedade de verdade — o controle parece acionável, a confiança parece vaga.
- **Culpa** — os ecos. A própria voz, devolvida no momento errado.
- **Impotência** — a retirada de opções. O botão único.
- **Esperança tensa** — a espera com a tentação de desistir. O final feliz como algo sustentado, não obtido.
- **Horror quieto** — na tesoura, linguagem clínica, sem melodrama, e a dupla confirmação. Mais um detalhe: se a moça deu nome ao pássaro, a narração do final trágico *se recusa a escrevê-lo* — "havia um nome nesta história; ela nunca mais conseguiu dizê-lo, e por isso ele não está escrito aqui."

---

## Segunda versão (v2)

O que foi efetivamente construído: 20 cenas, 5 telas de final (1 feliz, 3 variações do agridoce, 1 trágico), 15 ilustrações em SVG, num arquivo único de 55 KB, ainda totalmente offline.

Duas variáveis ocultas sustentam a rejogabilidade: o **aperto** (0 a 3) e os **ecos** (se nomeou o pássaro, se o alimentou na mão, se fechou a janela na tempestade). Elas não multiplicam rotas — multiplicam leituras da mesma rota, que é mais barato de manter e mais rico de sentir.

Há ainda uma recompensa para quem confia o jogo inteiro: chegar ao final feliz com aperto zero — sem nunca ter apertado o pássaro uma só vez — desbloqueia um parágrafo secreto em que ele faz ninho na mangueira do quintal, a mesma árvore que o derrubou no começo. Silenciosa de propósito; só aparece para quem mereceu.

O rastreador de finais ganhou duas linhas: as três categorias (feliz / agridoce / trágico) e, depois do primeiro agridoce, as três variações internas dele — o que dá ao jogador um motivo concreto para reabrir o arquivo.

Uma ideia foi deliberadamente cortada: a quebra de moldura em segunda pessoa no final trágico ("foi rápido — você escolheu rápido"). Era poderosa, mas transferia a culpa da personagem para o leitor de forma explícita demais para uma fábula. No lugar dela, ficou a versão mais contida do mesmo efeito — a narração que não consegue dizer o nome.

---

## Arquitetura técnica

O projeto é um único arquivo HTML, sem dependências, sem build, sem servidor. Essa restrição não é preguiça; é requisito de produto. Tinha que abrir em qualquer celular e viajar inteiro por WhatsApp, então tudo — texto, lógica, ilustrações — mora no mesmo arquivo.

**Dados separados do motor.** A história vive num objeto `STORY` declarativo: cada cena tem cor de céu, ilustração, blocos de texto e escolhas. O motor não sabe nada sobre pássaros; só sabe renderizar cenas e seguir escolhas. Isso torna a edição da narrativa independente da lógica — dá para reescrever qualquer cena sem tocar no código que a exibe.

**Texto condicional.** Cada bloco de texto pode carregar uma condição (`grip>=2`, `named`, `motive==love`). O motor avalia a condição contra o estado atual e mostra só o que se aplica. É esse mecanismo que faz a mesma cena soar diferente conforme o aperto acumulado, e que faz os ecos e as confissões funcionarem sem duplicar cenas inteiras.

**Estado mínimo.** Quatro variáveis (`named`, `hand`, `stormClosed`, `grip`) mais o `motive` da confissão atual. O `grip` soma silenciosamente a cada escolha de controle; o `motive` é resetado ao voltar de um final, para não vazar entre percursos.

**Ilustrações como código.** As 15 imagens são SVG escritos à mão, embutidos no arquivo — vetores que descrevem o pássaro, a gaiola, a tempestade. Por serem código e não imagens binárias, mantêm o arquivo leve e único. Se um dia o projeto quiser arte gerada ou pintada, a troca é local: cada SVG vira uma imagem em base64 e nada mais muda.

**Sem armazenamento de navegador.** Nenhum `localStorage` ou `sessionStorage` — não funcionariam em todo contexto de visualização e não são necessários. O progresso vive na memória da sessão, o que é suficiente para uma leitura de uma sentada.

**Sistema bilíngue.** Cada string carrega as duas línguas (`{pt, en}`); um toggle troca o idioma em tempo real, inclusive no meio de uma cena, sem perder o lugar.

### Validação

Como o jogo é um grafo de cenas, os erros perigosos são estruturais: uma escolha que aponta para uma cena inexistente, uma cena inalcançável, uma condição mal escrita, um final esquecido em alguma língua. Para isso foi escrito um validador à parte que: confirma que o JavaScript inteiro faz parse; percorre o grafo a partir da cena inicial e acusa qualquer cena órfã; verifica que todo destino de escolha existe; checa que toda condição segue a gramática esperada; e garante que os dois idiomas estão presentes em cada bloco. A v2 passou limpa: 20 cenas, 5 finais, 15 ilustrações, tudo alcançável.

---

## Decisões e tradeoffs em aberto

**Três finais, não mais.** A tentação de abrir mais ramos foi resistida. Profundidade emocional veio das variações internas e das variáveis ocultas, não da contagem de finais — é mais sustentável e evita o efeito catálogo.

**O caminho da confiança é de baixo atrito de propósito.** Quem joga estrategicamente vai notar que confiar é uma sequência de quatro escolhas "certas" quase sem resistência. Isso pode soar fácil demais. É intencional: confiar parece fácil de fora; o jogo só revela o custo na espera, quando já não há o que clicar. Se em playtest o ritmo soar leve demais, a correção pronta é fazer a tentação da janela aparecer duas vezes, dobrando a aposta sobre a paciência.

**Próximos passos possíveis:** testar o ritmo com leitores reais antes de mexer em qualquer coisa; eventualmente substituir os SVG por arte autoral; e, se fizer sentido, uma linha de créditos com o nome do autor antes de o arquivo circular.

---

*Estado atual: v2 funcional, validada, pronta para playtest. v1 preservada para comparação.*
