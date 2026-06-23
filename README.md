# A Moça e o Pássaro

Uma ficção interativa sobre amor, cuidado e a linha tênue entre proteger e prender.

> Uma mulher encontra um pássaro filhote, cria-o, dá-lhe o melhor de tudo. Quando o pássaro cresce e aprende a voar, ela tem medo de que ele vá embora e não volte. O que ela faz com esse medo decide tudo.

**[▶ Jogar agora](https://ottoboop.github.io/a-menina-e-o-passaro/)** *(GitHub Pages — veja a seção [Como publicar](#como-publicar))*, ou simplesmente abra o arquivo [`index.html`](index.html) em qualquer navegador.

---

## O jogo

É uma fábula jogável de uma sentada: 20 cenas, 5 finais, 15 ilustrações desenhadas em SVG. Tudo cabe num único arquivo HTML de ~55 KB, sem instalação, sem internet, sem dependências. Abre em qualquer celular e viaja inteiro por uma mensagem de WhatsApp.

- **Bilíngue** — português e inglês, com um toggle que troca o idioma em tempo real, no meio de uma cena, sem perder o lugar.
- **Offline** — texto, lógica e arte moram todos no mesmo arquivo. Não há servidor, nem build, nem armazenamento de navegador.
- **Rejogável** — o final que você alcança depende menos de uma única escolha e mais de quem você foi ao longo do caminho.

### Sobre o que é

No conceito original há três caminhos. No **bom**, ela deixa o pássaro livre e ele volta de vez em quando — porque gostou do que ela fez por ele. No **neutro**, ele arrebenta a gaiola e some, sem voltar. No **pior**, ela corta as asas para impedi-lo de voar, e ele morre.

O coração da fábula está num detalhe: *no final bom, o pássaro volta porque gostou do cuidado.* O mesmo cuidado que faz o pássaro voltar é o que, administrado com medo, vira gaiola. Cuidado é ao mesmo tempo o motor do retorno e o álibi do controle. O jogo inteiro existe para fazer você **sentir** essa ambivalência, não para rotulá-la.

### Como jogar

Não há nada a instalar. Você lê e escolhe — cada escolha é uma expressão de quem você é, não um cálculo de estratégia. Não procure a "resposta certa": o jogo nunca tranca um final por uma decisão isolada. O horror, quando vem, é retrospectivo — você chega ao fim, olha para trás e percebe o que construiu, uma decisão sensata de cada vez.

Há finais e leituras escondidos para quem confia o jogo inteiro. Confiar parece fácil de fora; o custo só aparece quando já não há o que clicar.

---

## A criação

Este projeto é também um pequeno estudo de design: como traduzir emoção em estrutura de escolha, em vez de descrevê-la com adjetivos. O registro completo está em [`docs/desenvolvimento.md`](docs/desenvolvimento.md). Em resumo:

### O diagnóstico que reorganizou tudo

A primeira versão (v1) entregou o conceito ao pé da letra — 9 cenas, 3 finais, bonita e funcional —, mas estava errada onde mais importava. As escolhas operavam como um roteador ("gaiola ou céu?"), com a resposta moralmente correta visível de longe. O jogador não *vivia um medo*; ele *escolhia um final*.

A tese que guiou a reescrita cabe numa frase: **o jogador nunca deve escolher "prender" — deve escolher "proteger".** Cada passo em direção à gaiola precisa parecer razoável, quase carinhoso, no instante em que é dado. Fechar a janela numa noite de tempestade não é crueldade; é cuidado. O horror não está em nenhuma escolha isolada — está na soma.

Daí o princípio de método: **emoção em ficção interativa se demonstra pela estrutura da escolha, não pelo adjetivo.** Não se escreve "ela sentiu medo"; constrói-se uma escolha cuja própria forma é o medo.

### As mecânicas

- **O aperto** — um contador invisível de medo (0 a 3). Não tranca finais; tinge a narração. Com aperto alto, a gaiola chega quase inevitável — e foi o jogador quem tornou isso verdade, sem nunca clicar em "comprar gaiola".
- **Os ecos** — escolhas do primeiro ato voltam citadas nos momentos finais. *"Só esta noite, você disse — as janelas aprendem rápido."* Culpa não se descreve; cobra-se.
- **As confissões** — antes de cada final, uma escolha que não muda a rota, só a última linha. Na tesoura, as duas opções de corte *são* a confissão: "é para protegê-lo" / "ele é meu".
- **Impotência e dupla confirmação** — a cena da espera tem um único botão. O final trágico, por outro lado, exige assinatura: nunca é um tropeço.
- **A espera com tentação** — a peça central. Depois de soltar o pássaro, vem a espera, e a opção de desistir. Ceder transforma o final feliz num final cruel. Confiar passa a exigir confiar *duas vezes*.

### Por baixo do capô

- **Arquivo único, sem build.** Não é preguiça — é requisito de produto. Tudo (texto, lógica, ilustrações) num só HTML para abrir em qualquer celular e viajar por mensagem.
- **Dados separados do motor.** A história vive num objeto `STORY` declarativo. O motor não sabe nada sobre pássaros; só renderiza cenas e segue escolhas. Dá para reescrever qualquer cena sem tocar no código.
- **Texto condicional.** Cada bloco pode carregar uma condição (`grip>=2`, `named`, `motive==love`). É isso que faz a mesma cena soar diferente conforme o aperto acumulado, sem duplicar cenas.
- **Estado mínimo.** Quatro variáveis (`named`, `hand`, `stormClosed`, `grip`) mais o `motive` da confissão atual.
- **Ilustrações como código.** As 15 imagens são SVG escritos à mão e embutidos — vetores leves, não imagens binárias. Trocar por arte pintada um dia é uma mudança local.
- **Sem armazenamento de navegador.** O progresso vive na memória da sessão — suficiente para uma leitura de uma sentada.

### Validação

Como o jogo é um grafo de cenas, os erros perigosos são estruturais. Um validador à parte confirma que o JavaScript faz parse, percorre o grafo a partir da cena inicial e acusa cenas órfãs, verifica que todo destino de escolha existe, checa a gramática das condições e garante os dois idiomas em cada bloco. A v2 passou limpa: 20 cenas, 5 finais, 15 ilustrações, tudo alcançável.

---

## Estrutura do repositório

```
.
├── index.html               # o jogo — abra este arquivo
├── docs/
│   └── desenvolvimento.md    # registro completo de design e desenvolvimento
└── README.md
```

## Como publicar

O jogo é estático: qualquer hospedagem de arquivos serve. Para usar o **GitHub Pages**:

1. Vá em **Settings → Pages** no repositório.
2. Em **Source**, escolha a branch (`main`) e a pasta raiz (`/root`).
3. Salve. Em alguns instantes o jogo estará no ar em `https://<usuário>.github.io/<repositório>/`.

Para compartilhar offline, basta enviar o próprio `index.html` — ele é autossuficiente.

---

*Estado atual: v2 funcional, validada, pronta para playtest.*
