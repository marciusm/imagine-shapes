# Manual · IMAGINE SHAPES

Criado por [Marcius Monteiro](https://marciusm.com) · [← voltar à apresentação](../README.md)

Este é o manual completo: cada forma, aba, atalho e detalhe de funcionamento. Para uma visão geral, com imagens, veja o [README](../README.md). Para ver a ferramenta em uso, assista ao [tutorial em vídeo](video/tutorial.mp4) (1 min 32 s, com legendas em português e inglês).

IMAGINE SHAPES é um motor de formas generativas em camadas. Grades, raios, fluxos, ruído, isométricos, distorções, formas orgânicas, física e padrões são camadas que se combinam em composições. O tempo das animações é musical (BPM e compassos, loop que fecha sem corte), tudo é reproduzível pela semente e cada quadro sai em SVG vetorial, PNG ou vídeo.

Um arquivo só, sem dependências: abra `index.html` no Chrome ou no Edge. O projeto e os SVGs importados ficam guardados no navegador, separados por endereço: o que está salvo abrindo o arquivo direto não aparece se a ferramenta for aberta por um site, e o contrário também vale. Para levar de um para o outro, use SALVAR JSON e ABRIR JSON (aba PROJETO).

## Camadas

Todas as formas foram escritas para esta ferramenta. Cada gerador desenha com a caneta vetorial (veja [SVG](#svg)), então aparece igual na vista, no PNG, no vídeo e no SVG.

| Família | Camada | O que desenha | O que se move | O que o som move |
|---|---|---|---|---|
| Grade | Truchet | peças que se encaixam em qualquer giro: arcos, diagonais, triângulos, quartos de círculo, pontes, pontilhado | as peças giram em cliques de 90° | espessura do traço |
| Grade | Bauhaus | quadrados que se dividem em quatro (subdivisões e chance de dividir), cada um com uma figura: círculo, quarto, meia-lua, triângulo, listras, anel | giros em cliques; troca de cores no tempo | (use os giros) |
| Grade | Meio-tom | grade quadrada ou hexagonal de pontos (círculo, quadrado, losango, linha, cruz, anel) cujo tamanho segue um campo: radial, linear, ruído, ondas, anel, xadrez | o campo anda; centro móvel | tamanho dos pontos |
| Radial | Coroa de barras | barras que saem de um centro, inteiras ou em segmentos, com afinamento; comprimento por ruído, ondas, espelhado, degraus, aleatório | giro, variação no tempo, pulso no tempo | comprimento das barras |
| Radial | Anéis | anéis concêntricos em arcos, tracejado, pontos, sólido ou marcas | cada anel gira um número inteiro de voltas por loop, alternando o sentido | raio dos anéis de fora |
| Radial | Rosácea | rosácea, hipotrocoide, epitrocoide, Lissajous e harmônica, com cópias giradas | a fase da curva varia e volta | tamanho |
| Fluxo | Campo de fluxo | linhas que seguem um campo de ruído, partindo espalhadas, em grade, em círculo, da borda ou do centro | o campo evolui e fecha no loop; linhas que crescem e voltam | comprimento das linhas |
| Fluxo | Linhas de onda | linhas paralelas que sobem em ondas e ruído; com Montanhas, cada uma cobre as de trás | as ondas andam | altura das ondas |
| Fluxo | Curvas de nível | isolinhas de um relevo de ruído (marching squares), com uma a cada N destacada | o relevo evolui | desloca os níveis |
| Ruído | Campo de pixels | pixels ligados pelo ruído: limiar, pontilhado Bayer, tamanho ou dois níveis | o ruído evolui | acende mais pixels |
| Ruído | Pontilhismo | milhares de pontos espalhados pela densidade de um campo | cada ponto respira no seu tempo; tremor opcional | tamanho dos pontos |
| Ruído | Barras | equalizador, código de barras, degraus ou medidor de LED, com picos na segunda cor | as alturas evoluem | altura das barras |
| Isométrico | Cubos | colunas em perspectiva isométrica, com topo e lados em três tons e contorno | as alturas sobem em ondas, ruído, pirâmide ou degraus | altura das colunas |
| Isométrico | Malha triangular | triângulos soltos, cubos de três tons, hexágonos ou estrelas sobre a malha | as peças aparecem e somem com o campo | (use o movimento) |
| Isométrico | Colmeia | hexágonos com três arcos ligando lados vizinhos (arcos, retas, pétalas, cordas) | as peças giram em cliques de 60° | espessura do traço |
| Distorção | Moiré | dois conjuntos iguais de anéis, linhas, raios ou espirais, um sobre o outro | o segundo orbita e balança | distância entre os centros |
| Distorção | Grade deformada | grade de linhas, pontos ou xadrez dobrada por lente, redemoinho, ondas, ruído ou pinça | a deformação passeia numa órbita | força da deformação |
| Distorção | Fatias | uma figura ou uma palavra cortada em fatias que deslizam (seno, ruído, escada, alternado, torção) | as fatias deslizam | deslocamento das fatias |
| Orgânico | Formas orgânicas | contornos fechados deformados por ruído, um dentro do outro, em contorno, alternado, sólido ou camadas de cor | os contornos evoluem; giro | ondulação |
| Orgânico | Filotaxia | pontos pelo ângulo de ouro, com qualquer figura e orientação radial, fixa ou tangente | onda de tamanho; giro; pulso | tamanho |
| Orgânico | Ramificação | árvore, coral radial ou raio, com níveis, abertura, variação e pontas | os galhos balançam; o raio muda a cada batida | balanço dos galhos |
| Física | Harmonógrafo | o traço de dois pêndulos amortecidos, um por eixo, mudando de cor ao longo do traço | a fase dos pêndulos varia e volta | tamanho |
| Física | Órbitas | corpos em órbitas elípticas pela lei de Kepler, vistos inclinados, com órbitas e rastro | cada corpo dá um número inteiro de voltas no loop; precessão | tamanho dos corpos |
| Física | Linhas de campo | linhas de força entre cargas positivas e negativas | as cargas passeiam e as linhas se refazem | movimento das cargas |
| Forma | Figura | uma figura sozinha (círculo, quadrado, triângulo, anel, cruz, estrela, polígono, losango, pétala, meia-lua, gota, quarto de círculo, barra), com repetições concêntricas | giro, pulso no tempo, respiração | tamanho |
| Forma | Carimbo | repete uma figura ou um SVG seu em grade, colmeia, anéis, espiral, espalhado ou onda, variando tamanho, rotação e cor | giro de cada forma, pulso, variação no tempo | tamanho das formas |
| Forma | SVG importado | um arquivo SVG seu, inteiro | respirar, balançar, flutuar, girar em passos, deslizar ou ladrilho deslizante; giro e pulso | tamanho |
| Padrões | Trama | fitas horizontais e verticais que passam por cima e por baixo, com folga e listras opcionais | a trama corre na diagonal, ou as fitas ondulam de largura | largura das fitas |
| Padrões | Chevron | faixas em zigue-zague empilhadas, em duas cores, três cores ou sorteadas | as faixas correm em sentidos opostos, avançam em passos ou respiram na altura do dente | altura do dente |
| Padrões | Células recuadas | quadros encaixados em cada célula, em degradê ou só contorno, com arredondamento | o fundo de cada célula se desloca com um ruído que fecha no loop | deslocamento do fundo |
| Padrões | Mosaico triangular | triângulos numa grade isométrica, em duas ou três cores, preenchidos ou só contorno | as cores mudam com um ruído que corre, ou em passos a cada batida | equilíbrio das cores |
| Padrões | Fitas torcidas | fitas que atravessam a tela torcendo no próprio eixo, com frente e verso em cores diferentes | as torções correm, com atraso de uma fita para a outra; a ondulação dá uma volta por loop | largura das fitas |
| Padrões | Ladrilhos deslizantes | ladrilhos com um desenho (meio círculo, círculo, quadrado, diagonal, listras), parte deles com fundo próprio | linhas e colunas deslizam uma casa por vez, alternando o sentido, e voltam ao lugar no fim do loop | tamanho do desenho |
| Padrões | Pontos no fluxo | grade de círculos, quadrados ou traços | cada ponto é empurrado por um campo de fluxo e muda de tamanho; o campo fecha no loop | tamanho dos pontos |
| Tipo e moldura | Fundo | uma cor chapada na tela inteira | | |
| Tipo e moldura | Texto | texto em IBM Plex Mono, com códigos | pulso; revelação letra por letra ou embaralhada | tamanho |
| Tipo e moldura | Moldura | borda, marcas de corte, réguas, grade de colunas e quatro textos nos cantos | | |

### Comum a todas as camadas

- **Opacidade e mistura** (normal, multiplicar, tela, sobrepor, diferença, exclusão, clarear, escurecer, somar). Valem na vista, no PNG, no vídeo e no SVG (como `opacity` e `mix-blend-mode` do grupo).
- **Semente:** o número que decide todo o acaso da camada. VARIAR (tecla R) sorteia outra; Shift + R sorteia para a composição inteira.
- **Reação ao som:** a faixa (graves, médios, agudos, energia, ataques ou nenhum) e o ganho (0 a 3). Embaixo, o texto "O som mexe em" diz o que muda naquela forma.
- **Cores:** cada parâmetro de cor escolhe uma função da paleta (fundo, primária, secundária, acento) ou "outra", com um hex próprio.
- **Posição:** nas camadas com centro, arrastar na vista move a camada. Ela gruda no centro e nos terços (Alt solta), e Shift trava o eixo. A roda do mouse muda o tamanho, e o duplo clique volta ao centro.
- **↺** ao lado de cada parâmetro volta ao valor padrão; RESTAURAR PADRÕES volta todos.

### Giros em cliques

Truchet, Bauhaus e Colmeia giram em passos de 90° (ou 60° na Colmeia):

- **Giros por loop:** quantas voltas inteiras cada peça dá no loop. 1 giro = 4 cliques de 90°, ou seja, um a cada 2 compassos com o loop padrão.
- **Atraso entre as peças:** onda (do centro para fora), cascata (sorteado), juntos ou diagonal.
- **Espalhamento do atraso:** 0,5 faz a onda atravessar a grade em meio passo. Mais que isso, sempre há peças girando.
- **Duração do giro:** a parte do passo usada no movimento. O giro começa no tempo forte e as peças param sempre em ângulos exatos.

## Composições de exemplo

| Composição | O que mostra |
|---|---|
| TRUCHET | arcos de Truchet em cartaz com moldura, borda e textos (nome, composição, SEED e BPM) |
| COROA | coroa de barras em segmentos dentro de anéis tracejados girando, com um círculo que pulsa no tempo |
| CAMPO | 1.500 linhas num campo de fluxo, com 5% em vermelho |
| TOPOGRAFIA | curvas de nível em cianotipia, uma a cada quatro destacada |
| CUBOS | colunas isométricas nas cores da Bauhaus, subindo em ondas |
| COLMEIA | Truchet hexagonal de cordas duplas em rosa e azul de risografia |
| MOIRÉ | anéis concêntricos sobre anéis concêntricos, o segundo em órbita |
| GIRASSOL | filotaxia de pétalas em terracota, com espirais de 21 em outra cor |
| HARMONÓGRAFO | harmonógrafo em azul noturno, mudando de cor ao longo do traço |
| CAMPO ELÉTRICO | linhas de campo entre cinco cargas que passeiam |
| BAUHAUS | a grade Bauhaus com subdivisões e giros em cascata |
| CORDILHEIRA | linhas de onda em montanhas, uma na frente da outra |
| MEIO-TOM | duas retículas hexagonais (radial e ruído) em multiplicação |
| FATIAS | um círculo em fatias deslizando, com o nome da ferramenta embaixo |
| ÓRBITAS | 34 corpos em órbitas de Kepler, com rastro |
| CARIMBO | círculos em espiral, menores perto da borda, em três cores, pulsando na batida |
| EQUALIZADOR | medidor de LED espelhado, com picos verdes; reage aos graves |
| RAÍZES | nove troncos ramificando do centro, balançando no tempo |
| LENTE | uma grade dobrada por uma lente que passeia |
| PIXELS | campo de pixels em pontilhado Bayer |
| TRAMA | fitas listradas em trama, correndo na diagonal |
| CHEVRON | faixas em zigue-zague em três cores, correndo em sentidos opostos |
| POÇOS | quadros encaixados em degradê, cujo fundo se desloca como num túnel |
| MOSAICO | triângulos em três cores, levados por um ruído que corre no loop |
| FITAS | dez fitas torcendo no próprio eixo, com frente e verso em duas cores |
| QUEBRA-CABEÇA | ladrilhos com meios círculos que deslizam em linhas e colunas e voltam ao lugar |
| CORRENTE | grade de pontos empurrada por um campo de fluxo |

Cada composição tem paleta própria. Duplique uma (⧉) e troque camadas, ou crie uma nova (+ NOVA). RECOMEÇAR, na aba PROJETO, volta às composições de exemplo e mantém os SVGs importados.

## Uso

- **Esquerda:** composições e camadas. A lista de composições tem rolagem própria e o título mostra quantas são, para as camadas continuarem à vista. Clique numa camada para editar na aba CAMADA. As camadas são listadas de cima para baixo (a de cima cobre as de baixo). Arraste para reordenar, ou use ↑ ↓. A lista mostra o tempo de desenho de cada camada (em laranja as que passam de 40% do tempo do quadro). Uma camada que dá erro ganha um ⚠, com a mensagem ao passar o mouse.
- **Aba CAMADA:** os parâmetros da camada selecionada, em seções (FORMA, MOVIMENTO, COR…).
- **Aba FORMAS:** a biblioteca, com uma miniatura de cada forma na paleta da composição. Clicar adiciona a forma acima da camada selecionada. Embaixo fica a seção SEUS SVGS.
- **Aba PROJETO:**
  - nome;
  - formato da tela (quadrado, retrato 4:5, vertical 9:16, paisagem HD e 4K, quadrado grande, cartaz A3 a 150 dpi, faixa de LED ou personalizado) e quadros por segundo;
  - tempo: BPM, compassos por loop e loop ligado ou desligado;
  - semente do projeto;
  - arquivo: SALVAR JSON, ABRIR JSON e RECOMEÇAR.
- **Aba CORES:** as 12 paletas, as quatro cores da composição, INVERTER (troca fundo e primária), SORTEAR (paleta nova) e USAR EM TODAS.
- **Aba SOM:** música (guardada neste navegador), microfone, reação geral e o medidor das cinco faixas.
- **Aba AO VIVO:** janela de saída, blackout, transição e diretor automático (veja [Ao vivo](#ao-vivo)).
- **Aba MIDI:** liga o MIDI, aprende controles e lista o que está ligado (veja [MIDI](#midi)).
- **Aba EXPORTAR:** PNG, SVG, COPIAR SVG, MP4, WebM, sequência PNG e JSON.
- **Ajuda nas abas:** o (?) ao lado do nome de cada seção abre um balão com a explicação; clicar fora ou Esc fecha.
- **Desfazer e refazer:** ⌘Z e ⇧⌘Z (ou ↶ ↷ no cabeçalho), até 150 passos. Trocar a composição selecionada não conta como edição.
- **Zoom da prancheta:** FIT, 100% (um pixel do projeto por pixel da tela), − e + no cabeçalho, ou ⌘− e ⌘+ (⌘0 volta a FIT). É só a vista: não muda o que é exportado.
- **Guias** (tecla G): terços, centro e margem de 5%, desenhados só na vista.

| Tecla | Ação |
|---|---|
| Espaço | toca e pausa a animação |
| ← → | um quadro (Shift: dez) |
| ↑ ↓ | seleciona a camada de cima ou de baixo |
| 0 | volta ao início do loop |
| 1 a 9 | troca a composição, com a transição da aba PROJETO |
| [ ] · , . | composição anterior e seguinte, com a mesma transição (Page Up e Page Down também, para usar um passador de slides) |
| D | liga e desliga o diretor automático |
| R | nova variação da camada selecionada |
| Shift + R | nova variação da composição inteira |
| S | salva PNG (na escala da aba EXPORTAR) |
| Shift + S | salva SVG |
| M | toca e pausa a música |
| G | guias |
| B | blackout da vista e da janela de saída |
| H | só a vista |
| F | tela cheia |
| Delete | apaga a camada selecionada (⌘Z desfaz) |
| ⌘Z · ⇧⌘Z | desfaz e refaz |
| Esc | fecha a ajuda e os balões; sai do modo aprender do MIDI |
| ? | ajuda |

URL: `?comp=4` abre a composição 4; `?size=1080x1920` troca o formato; `?clean` abre só a vista; `?lang=en` ou `?lang=pt` escolhe o idioma; `?nohelp` pula a tela de abertura.

### Idioma

Os botões PT e EN, no topo e na tela de abertura, trocam o idioma da interface. A escolha fica salva no navegador; na primeira abertura, vale o idioma do navegador.

O projeto não muda de idioma: as composições de exemplo continuam guardadas em português e são mostradas traduzidas. Os nomes de camada e de composição que você digitar ficam como estão.

## Códigos de texto

As camadas Texto e Moldura trocam `{CÓDIGO}` pelo valor do momento. Os botões embaixo do campo inserem o código onde está o cursor.

| Código | Valor |
|---|---|
| `{NAME}` | nome do projeto |
| `{COMP}` | nome da composição |
| `{N}` | número da composição (01, 02…) |
| `{SEED}` | código da variação da composição (muda com VARIAR) |
| `{BPM}` | BPM |
| `{DATE}` | data de hoje, DD.MM.AA |
| `{TIME}` | tempo no loop |
| `{FRAME}` | quadro |
| `{SIZE}` | tamanho da tela |
| `{LAYERS}` | número de camadas |

## Cores

Cada composição tem a própria paleta de quatro cores: fundo, primária, secundária e acento. As camadas pedem cores pela função, então trocar a paleta recolore a composição inteira. As 12 paletas prontas são: PAPEL, TINTA, MONO, BAUHAUS, RISO, ÁCIDO, CIANOTIPIA, TERRACOTA, NOITE, SINAL, MENTA e GIZ. Os campos de cor usam um seletor próprio (o nativo do Mac abre uma janela que não fecha ao clicar fora), com as cores da paleta à mão.

## Som

- **Música:** ESCOLHER ÁUDIO… (MP3, WAV, M4A, OGG, FLAC…) ou solte o arquivo na vista. A faixa é decodificada e analisada de uma vez, com FFT de 2.048 pontos, 30 leituras por segundo:
  - graves: 20 a 150 Hz;
  - médios: 150 a 2.000 Hz;
  - agudos: 2 a 10 kHz;
  - energia;
  - ataques, pelo fluxo espectral.
  
  Cada faixa é normalizada pelos percentis da própria música.
- **Tocando** (TOCAR MÚSICA no rodapé, TOCAR na aba SOM ou tecla M), a animação segue o relógio da música. Sem música carregada, o botão do rodapé abre a escolha do arquivo. Pausada, a animação volta ao relógio próprio e deixa de reagir. O botão Som liga e desliga o áudio sem parar a reação.
- **Microfone:** reage ao vivo, com normalização automática. Com música e microfone juntos, vale o maior dos dois.
- **Reação:** liga e desliga a reação de todas as camadas, e o ganho geral multiplica todas.
- **Arquivo da música:** fica guardado neste navegador (IndexedDB) e volta sozinho quando a ferramenta abre de novo; TIRAR apaga. O JSON não leva a música, e cada navegador guarda a sua.

## SVG

A exportação SVG desenha a composição de novo, pela mesma caneta, no destino SVG:

- Cada camada vira um `<g>` com o nome da camada (`inkscape:label`, camada no Inkscape), `opacity` e `mix-blend-mode`.
- Formas seguidas com o mesmo estilo saem num só `<path>`, em lotes de até 8.000 números. Assim o arquivo continua leve e abre rápido em outros programas.
- Os recortes (Fatias, Bauhaus girando, margens) viram `<clipPath>`.
- O texto vira `<text>` em IBM Plex Mono. Em outra máquina, instale a fonte ou converta o texto em contornos no editor.
- Os SVGs importados entram uma vez como `<symbol>` e são reaproveitados com `<use>`.
- Desligue a camada Fundo para exportar com fundo transparente.
- COPIAR SVG põe o código na área de transferência. Dá para colar direto no Figma.

O SVG é o quadro atual (o mesmo do PNG). Para animação, use MP4, WebM ou a sequência PNG.

## SVG importado

IMPORTAR SVG… (aba FORMAS) ou solte um ou mais arquivos .svg na vista. Cada arquivo:

- **é limpo:** saem `script`, `foreignObject`, `iframe`, animações, atributos de evento (`onload`, `onclick`…), links `javascript:`, imagens e `url()` externos e `<style>` com `@import`;
- **ganha ids com prefixo próprio**, e as referências são corrigidas, para que dois arquivos não se atrapalhem;
- **fica guardado no projeto** e vai junto no JSON (até 4 MB por arquivo).

Uso:

- **+ CAMADA:** cria uma camada SVG importado. Ela tem posição, tamanho, rotação, giro, espelho, pulso e um movimento próprio (seção MOVIMENTO): respirar, balançar, flutuar, girar em passos, deslizar ou ladrilho deslizante na diagonal, com intensidade e ciclos por loop.
- **+ CARIMBO:** cria um Carimbo com o arquivo como forma. O arquivo também aparece na lista Forma de qualquer Carimbo.
- **Cor:** "paleta" troca todos os fill e stroke (menos `none` e gradientes) pela cor escolhida; "original" mantém as cores do arquivo.
- **×** apaga o arquivo. Se ele estiver em uso, a ferramenta pede confirmação.

## Exportação

- **PNG:** o quadro atual, na escala escolhida (1× a 4×; um projeto 1080×1080 em 4× sai em 4320×4320). A tecla S usa a mesma escala.
- **SVG:** veja [SVG](#svg).
- **MP4** (aba EXPORTAR, seção VÍDEO MP4): o motor desenha quadro a quadro, sem perder quadros, e codifica no próprio navegador com WebCodecs (H.264). O contêiner MP4 é montado no próprio index.html, sem bibliotecas.
  - Formatos: projeto atual, Instagram Reels e Stories 9:16 (1080×1920), feed 4:5 (1080×1350), quadrado 1:1, Full HD 16:9 e 4K. Outro formato reorganiza a composição na hora, porque as medidas são relativas.
  - Composições: só a atual, ou seguir o diretor: a mesma regra da aba AO VIVO (a cada quantos compassos, ordem e composições marcadas), começando pela composição atual e com a transição da aba AO VIVO.
  - Duração: em loops (fecham sem emenda), em segundos, a música inteira ou, seguindo o diretor, uma volta (cada composição marcada uma vez).
  - Qualidade: Alta, Média ou Leve (≈0,2, 0,1 ou 0,05 bit por pixel).
  - Música no vídeo: AAC 48 kHz estéreo, ou Opus quando o navegador não tem AAC. A reação ao som no vídeo vem da análise da faixa, então fica igual à da vista. O atraso de partida do codificador AAC é medido e compensado, para o som cair no quadro certo.
- **WebM:** grava um loop em tempo real (MediaRecorder), do jeito que aparece na vista, com a música se houver. É um rascunho rápido.
- **Sequência PNG:** do quadro A ao B, em ZIP (sem compressão, já que o PNG é comprimido). Para virar vídeo: `ffmpeg -framerate 30 -i %05d.png -c:v libx264 -pix_fmt yuv420p loop.mp4`.
- **JSON:** o projeto inteiro, com os SVGs importados.

## Ao vivo

Tudo na aba AO VIVO.

- **Janela de saída:** abre uma janela só com a prancheta, para arrastar ao projetor ou à segunda tela. O duplo clique nela põe em tela cheia, o cursor some e as teclas da ferramenta funcionam nela.
- **Troca de composição:** as teclas 1 a 9 trocam com uma fusão (duração em Transição). [ ] ou , . vão para a composição anterior e a seguinte, e Page Up e Page Down fazem o mesmo, para usar um passador de slides. Clicar na lista troca na hora.
- **Blackout** (tecla B): escurece a vista e a janela de saída com meio segundo de fade. Não mexe no que é exportado.
- **Diretor automático** (tecla D, ou DIRETOR no rodapé): troca de composição a cada 1, 2, 4, 8 ou 16 compassos. A troca acontece no começo do compasso, pelo relógio da animação, que segue a música quando ela toca (sem música, vale o BPM do projeto), com a transição acima.
  - Ordem: a da lista ou aleatória. A aleatória passa por todas as composições marcadas antes de repetir e nunca repete a mesma em seguida.
  - Composições que entram: os botões numerados ligam e desligam cada uma (TODAS e NENHUMA ajudam). A escolha fica salva no projeto.
  - No último compasso antes da troca, a próxima composição pisca na lista, e a aba AO VIVO mostra quantos compassos faltam.
  - Com a animação pausada, o diretor espera. Trocar à mão (teclas, lista ou MIDI) ou pular no tempo recomeça a contagem.
  - No MP4 (aba EXPORTAR), "Seguir o diretor" calcula a mesma regra pelo número do quadro, a partir da composição atual. Na ordem aleatória, o sorteio vem da semente do projeto, então o vídeo sai igual em qualquer máquina.

## MIDI

- **Ligar:** LIGAR MIDI pede a permissão do navegador. A linha de cima mostra os controladores conectados; um cabo ligado depois aparece sozinho. Funciona no Chrome e no Edge (o Safari não tem Web MIDI). Com controles já ligados e a permissão dada antes, o MIDI liga sozinho quando a ferramenta abre.
- **Aprender:** APRENDER e depois clique no que quer comandar: um parâmetro numérico, liga/desliga ou de lista na aba CAMADA; a opacidade da camada; uma composição na lista à esquerda; ou uma das ações (PLAY/PAUSA, MÚSICA, ANTERIOR, PRÓXIMA, BLACKOUT, DIRETOR, VARIAR). Depois mova um knob ou aperte um pad. No modo aprender, clicar num controle só escolhe o alvo, sem mudar o valor. Esc sai do modo aprender.
- **Pads → composições:** liga o primeiro pad apertado e os seguintes (notas em sequência) às composições 1 a 16.
- **Como cada controle age:**
  - knob em parâmetro numérico vai do mínimo ao máximo; em liga/desliga, liga acima da metade; em lista, escolhe a opção pela posição;
  - pad em liga/desliga alterna; em parâmetro numérico, leva ao máximo enquanto estiver apertado e volta ao soltar;
  - pad em composição ou ação dispara ao apertar. Um botão que manda CC (127 ao apertar) funciona como pad.
- **Lista:** cada ligação aparece com a mensagem (CC ou nota, número e canal) e o que ela comanda, com × para apagar. A última mensagem recebida aparece embaixo, para conferir o controlador.
- **Fica no projeto:** as ligações vão no JSON e apontam para a composição e a camada certas, mesmo se a lista mudar de ordem.

## Desempenho

- **Prévia automática:** quando um quadro passa do tempo dele, a vista desenha em 75% ou 50% da resolução e volta quando sobra folga. O rodapé da vista mostra o tamanho, os quadros por segundo, a qualidade da prévia e o zoom. As exportações saem sempre em 100%.
- **Só redesenha quando precisa:** quando o quadro muda, quando algo é editado ou com o microfone ligado.
- **Lotes da caneta:** fecham a cada 1.200 números no canvas. Um caminho com dezenas de milhares de formas deixa o preenchimento do canvas muito lento, e em lotes ele fica rápido. Nos testes, com 40 combinações aleatórias de parâmetros para cada gerador, o pior caso desenhou em menos de 200 ms.

## Estrutura do código

O `index.html` tem o HTML, o CSS e um script com estas partes, nesta ordem:

1. **Utilidades e idioma:** `T()` traduz pela tabela `EN_TXT` (uma entrada por linha, `português ⇒ inglês`), `TF()` traduz frases com valores (`'Quadro {0} de {1}'`) e `L2(pt, en)` serve para os textos longos. Para traduzir um texto novo, acrescente uma linha.
2. **Acaso:** `hash3` (hash inteiro com semente), `mulberry` (sequência), `noiseOf` (Perlin 3D por semente) e `fbm`.
3. **Tempo musical:** `loopSec`, `loopFrames` e `frameInfo` (`F.ph` de 0 a 1 no loop, `F.beat`, `F.pulse`, `F.a` com o som).
4. **Paletas:** `PALS` e `palOf`.
5. **Parâmetros:** `N` (número), `B` (liga/desliga), `S` (lista; pode ser uma função), `C` (cor), `TX` (texto) e `Hd` (título de seção), mais os grupos prontos (`pPos`, `pRot`, `pTurns`, `pEvolve`…).
6. **A caneta** (`class Pen`): estilo (`fill`, `stroke`, `both`, `set`), matriz (`push`, `pop`, `tr`, `rot`, `sc`), formas (`rect`, `rrect`, `circle`, `ring`, `ellipse`, `arc`, `sector`, `poly`, `lines`, `ngon`, `star`, `M`/`L`/`C`/`Q`/`A`/`Z`), `clip`, `text`, `image` e `end`. Os destinos são `cvTarget(ctx)` e `svgTarget()`.
7. **SVG importado:** `svgSanitize`, `assetAdd`, `assetPrep` (troca de cor) e `assetBmp` (cache em bitmap para o canvas).
8. **Ajudas dos geradores:** `grid`, `hexCells`, `clickTurn`, `delayOf`, `place` e `motif` (as figuras básicas).
9. **Geradores:** um `reg(tipo, rótulo, parâmetros, desenho, {info, snd, pos})` por forma, e `FAMILIES`.
10. **Projeto:** `examples` (composições de exemplo), `defaultProject`, `normalize`, `save`/`persist` (localStorage), `UNDO` e `MIGR` (mudanças aplicadas uma vez a projetos salvos por versões anteriores, como as composições novas).
11. **Motor:** `drawLayers` (opacidade e mistura por tela de apoio), `renderComp`, `render` (transição e qualidade da prévia), `renderMix` (a fusão entre duas composições, também usada no MP4 do diretor), `svgOf` (o SVG da composição), `blit` (a vista), janela de saída e `tick`/`rafLoop`.
12. **Som:** `SONG`, `songAnalyse` (FFT própria), `songValues`, `songKeep`/`songRestore`/`songForget` (a música guardada no IndexedDB), `AUD` e `micUpdate`.
13. **Interface:** os painéis (`renderParams`, `renderShapes`, `renderProject`, `renderColors`, `renderSound`, `renderLive`, `renderMidi`, `renderExport`), a ajuda, a tela de abertura e o seletor de cor. Junto das composições ficam o diretor (`DIR`; `dirTick` conta os compassos, `dirPick` escolhe a próxima e `dirSeq` monta a sequência do MP4) e o MIDI (`midiOn`, `midiMsg`, `midiBind`, `midiDo`; as ligações ficam em `P.midi.map`).
14. **Exportação:** `exportPng`, `exportSvg`, `exportSeq` (ZIP), `exportWebm` e `exportMp4`, com `mp4Build` e `audioTrack` (`aacPriming` mede o atraso do codificador AAC).
15. **Eventos e início:** `bind`, `onKey` e `boot`. No console, `window.shapes` dá acesso ao motor.

Por que um arquivo só: assim a ferramenta abre com duplo clique e vai para outra máquina copiando a pasta.

### Criar uma forma nova

Um `reg(...)` e uma entrada em `FAMILIES`. O desenho recebe a caneta `g` e `R = {p, F, W, H, S, u, pal, au, h, n3, ln}`:

- `p`: os parâmetros;
- `F`: o tempo;
- `S`: o lado menor da tela;
- `u`: a escala dos traços (`S/1080`);
- `au`: o som que chega na camada, de 0 a 2;
- `h(a, b, c)`: o hash com a semente da camada;
- `n3`: o ruído 3D;
- `ln(x, y, ciclos, raio)`: o ruído que fecha no loop.

```js
reg('dots','Grade · pontos',[
 Hd('FORMA'),N('div','Divisões',12,2,80,1),pLw(2),
 Hd('MOVIMENTO'),pSpeed(1),
 Hd('COR'),pCol()],
(g,R)=>{const p=R.p,G=grid(R,p.div,0.05);g.fill(col(R,p.color));
 for(let j=0;j<G.rows;j++)for(let i=0;i<G.cols;i++){
  const t=0.5+0.5*Math.sin(TAU*(R.F.ph*p.speed+(i+j)/G.cols));
  g.circle(G.ox+(i+0.5)*G.c,G.oy+(j+0.5)*G.c,G.c*0.45*t*(1+R.au*0.5))}},
{info:['Pontos que pulsam em diagonal.','Dots pulsing diagonally.'],snd:['tamanho','size']});
```

Depois, acrescente `'dots'` numa família de `FAMILIES` e os rótulos novos em `EN_TXT`. Para que o loop feche, use voltas inteiras: `R.F.ph * n` com `n` inteiro, ou `R.ln(x, y, n)` para o ruído.
