# Dev Shrine Page

> Uma página que finge ser só bonita, mas na verdade está te estudando.

Este repositório contém um experimento interativo feito com IA para devs curiosos: uma single page cheia de animações, quests, segredos, camadas escondidas e comportamentos que só aparecem quando você começa a **debugar a própria página**.

Nada aqui é “necessário” para funcionar. É tudo excesso proposital.

---

## Visão geral

A Dev Shrine Page é:

* Um *playground* para devs que gostam de abrir o DevTools.
* Um mini-ARG com:

  * **Quests visíveis** (UI),
  * **Quests ocultas** (apenas via console/localStorage),
  * **Modos especiais** (caçador, XRAY, ascensão, realidade quebrada…),
  * **Entidade meta** (oráculo / boss),
  * **Ecos de sessões passadas** (modo fantasma).
* Feita inteiramente em:

  * HTML estático,
  * CSS puro (sem frameworks),
  * JS vanilla (sem libs externas, sem bundler).

A ideia é que um dev ou youtuber de tecnologia possa passar **dezenas de minutos** explorando, reagindo, pausando a tela, indo e voltando, sem esgotar tudo na primeira visita.

---

## Como rodar

Nada de especial:

1. Clone ou baixe o repositório.
2. Abra o `index.html` diretamente no navegador
   (ou sirva com qualquer HTTP estático, tipo `npx serve`).
3. **Não precisa** de build, npm, bundler, nada.
   Só HTML + CSS + JS.

---

## Como começar a brincar (sem spoilers)

Você não “vence” a página. Você **negocia** com ela.

Sugestão de fluxo inicial:

1. **Navegue como um usuário normal.**

   * Leia os textos.
   * Passe o mouse sobre os elementos “suspeitos”.
   * Interaja com os botões óbvios.
2. Depois, **lembre que você é dev**:

   * Abra o DevTools.
   * Olhe o console.
   * Olhe os atributos `data-*`.
   * Procure por funções globais estranhas.
3. Em algum momento, a página vai deixar claro que:

   * Ela sabe que você abriu o console.
   * Ela sabe que você está tentando “trapacear”.
   * E ela vai te dar munição pra continuar.

### Regras autoimpostas (recomendadas)

Para se divertir mais, tente:

* Não sair abrindo o arquivo de código direto como “solução”.
* Tratar a página como um jogo:

  * **UI = superfície**,
  * **DevTools = dungeon**.
* Anotar/registrar:

  * Quests que você descobriu,
  * Comportamentos estranhos,
  * “Momento em que a página pareceu saber demais”.

Se quiser gravar conteúdo (react, video breakdown etc), esse mindset ajuda.

---

## Sistemas principais (sem explicar como ativar)

Abaixo está o mapa **do que existe**, não de **como ativar**.
Nada aqui traz a “resposta”, só o “tema” de cada camada.

### 1. Quests visíveis

* Há um **log de quests** na própria UI.
* Cada quest tem:

  * Um título,
  * Uma dica curta,
  * Um estado de completude.
* Algumas são óbvias (botões, interações visíveis).
  Outras exigem:

  * Ler descrições com atenção,
  * Reagir a micro-hints,
  * Clicar onde ninguém clicaria.

⚠️ Não existe botão “reset”.
Mas o estado é salvo em `localStorage`, então você pode limpar manualmente se quiser recomeçar do zero.

---

### 2. Quests ocultas

Além das quests visíveis, existe um conjunto de **“hidden quests”**:

* Não aparecem na UI.
* São rastreadas em um storage separado.
* Disparam em função de **comportamentos**:

  * Jeito que você usa o teclado/mouse,
  * Maneira como mexe na aba,
  * Como rola a página,
  * Como interage (ou não) com DevTools.

Elas **não são necessárias** para ver a superfície do shrine.
Mas são importantes se você quiser entrar em camadas mais profundas (oráculo, boss, fantasma, etc).

---

### 3. Modo Caçador & HUD

O **modo caçador**:

* Começa como um simples toggle na UI.
* Ganha camadas extras com scripts:

  * HUD de caça,
  * Radar de alvos “suspeitos”,
  * Sensor de proximidade ligado ao mouse,
  * Highlights em elementos misteriosos da página.

Experiência ideal:

* Ative o modo caçador,
* Passe o mouse devagar,
* Observe como o HUD reage ao que existe na tela.

---

### 4. XRAY Mode

Existe um modo “RX” da página:

* Ativado via atalho de teclado (não vou dizer qual).
* Localiza e destaca elementos com `dataset`,
* Desenha caixas e labels em cima de várias estruturas internas.

Bom para:

* Devs que gostam de “ver o layout como o navegador vê”.
* Youtubers que querem pausar o vídeo e analisar tudo o que está sendo revelado.

---

### 5. Ascensão

Quando você está **avançado o suficiente**:

* Um script de **ascensão** pode disparar:

  * Final secreto,
  * Mensagem de “endgame”,
  * Uma visão meta da página sobre a sua jornada.

Não é o fim do jogo.
É mais um tipo de “créditos falsos” para indicar que você entrou no **endgame do shrine**.

---

### 6. Modo Fantasma (Ghost Sessions)

A página lembra de você.

* Existe um sistema de **ghost sessions** que:

  * Salva traços das suas interações (sem dados pessoais).
  * Armazena isso em `localStorage`.
* Em visitas futuras:

  * Ecos de cliques que **não são seus** aparecem.
  * É como se outros devs (ou versões passadas de você) ainda estivessem por ali.

Existe também um **overlay de sessões fantasma** que pode ser aberto via console (nome da função está no código, não aqui 😏).

---

### 7. Oráculo de Dev

Em algum momento, você pode chamar uma entidade que:

* Analisa:

  * Seu uso de teclado e mouse,
  * Quantas quests você completou,
  * Quantas hidden quests foram detectadas,
  * Quantas sessões fantasma existem,
  * Se você já viu finais, boss, etc.
* E devolve:

  * Um mini “perfil” seu como dev dentro do shrine,
  * Comentários irônicos/metas,
  * Hints de coisas que você ainda não tocou (sem dizer exatamente como).

O nome dessa entidade é citado nos scripts e/ou no console.
Achar como chamá-la é parte da graça.

---

### 8. Echo da Sessão

Existe um comando que:

* Abre um overlay de **replay da sessão atual**.
* Ele conta:

  * O que você fez,
  * Em que ordem,
  * Em quanto tempo,
  * Com timestamps estilizados.
* E atribui uma “nota” para a sua run.

É um ótimo lugar para:

* Entender o que a página considerou importante,
* Depoimentos em vídeo (“olha o que o log acha que eu fiz”).

---

### 9. Break Reality (versão avançada)

O botão de “break reality”:

* Não é só um enfeite.
* Em determinado contexto:

  * Ele aciona um modo em que a UI:

    * Distorce,
    * Ganha efeitos de cor,
    * Textos glitcham,
    * Console fala estranho.
  * Tudo dura alguns segundos e se recompõe.

Dica de uso:

* Clique nele **quando já tiver entendido a “realidade normal” da página**.
* Observe o que muda *durante* e o que sobra *depois*.

---

### 10. Boss de Easter Egg

Existe um “boss”:

* Não aparece para quem está no começo.
* Faz sentido só quando:

  * Várias quests já foram feitas,
  * Várias hidden quests já foram detectadas,
  * Certas features avançadas já foram vistas.
* É um “evento” dividido em fases, que:

  * Reage a você ligar/desligar certos modos,
  * Usa os overlays existentes (XRAY, break reality, echo, etc),
  * E marca um “estado de vitória” próprio.

O gatilho principal é um comando no console com um nome óbvio, mas você precisa primeiro **merecer a atenção dele**.

---

## Dicas para jogar sem se auto-spoilar

* **Primeiro contato:** jogue só na superfície.
* **Segundo contato:** jogue com DevTools aberto (console, elements).
* **Terceiro contato:** aí sim, comece a:

  * Ler código JS,
  * Explorar `localStorage`,
  * Testar funções globais.

Se você quiser gravar:

* Uma run completamente “cega” (sem console),
* Depois uma run “dev” usando console,
* Depois uma “run de engenharia” destrinchando o código.

A página foi pensada para aguentar esses 3 estilos.

---

## Convenções internas (para devs que abrirem o código)

Algumas chaves de `localStorage` importantes:

* `dev-shrine-quests-v1` – quests visíveis.
* `dev-shrine-hidden-quests-v1` – hidden quests.
* `dev-shrine-ghost-sessions-v1` – sessões fantasma.
* `dev-shrine-boss-v1` / `dev-shrine-boss-cleared-v1` – boss.
* `dev-shrine-ascended-v1` – ascensão.
* Outros prefixos existem, mas você encontra explorando o JS.

Funções globais interessantes (sem descrever todas):

* Há funções de ajuda, oráculo, boss, ecos, scans, etc.
* Os nomes são intencionalmente **curtos e significativos**.
  Se você inspecionar `window`, vai reconhecer algo.

---

## Filosofia de design

* **Nada crítico está escondido atrás de uma API externa.**
  Toda a brincadeira cabe no próprio front-end.
* Tudo é pensado para ser:

  * Explorável via DevTools,
  * Comentável em vídeo,
  * Forkável e remixável.
* O objetivo não é “enganar o usuário”, e sim:

  * Recompensar a curiosidade do dev,
  * Misturar UX + código + storytelling.

---

## Quero mexer no projeto, e agora?

Sinta-se à vontade para:

* Adicionar novas quests,
* Inventar mais modos,
* Criar versões alternativas (temáticas),
* Ou até portar a ideia para outro stack.

Só mantenha a regra principal:

> “Nada aqui é obrigatório. Tudo é excesso proposital.”

---

## Por onde começar, se você for youtuber de tech

Sugestão de roteiro (sem spoilers técnicos):

1. Abra a página, reagindo como usuário normal.
2. Repare que ela está **um pouco séria demais** para ser só uma landing page.
3. Abra o console e leia o que ela fala.
4. Comece a descobrir:

   * Quests,
   * Modos,
   * Overlays.
5. Em algum momento, perceba que:

   * Ela sabe que você está gravando,
   * Ela guarda sessões,
   * Ela tem opinião sobre como você joga.

A partir daí, o vídeo se escreve sozinho.
