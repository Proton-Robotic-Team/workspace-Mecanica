# 03  Montagem e Hardware

> **Objetivo:** Entender que a parte mecânica não existe sozinha 
> e que o melhor projeto nasce de conversas longas e honestas com
> quem cuida do hardware.

---

## 1. Você chegou na parte boa

Se você leu os dois documentos anteriores, você já sabe:
- Medir um componente com precisão
- Olhar para um robô pronto e entender como ele foi construído
- Tirar dimensões de uma imagem e de um datasheet

Agora é hora de usar tudo isso para construir **o seu robô**.

E a primeira coisa que você precisa entender é:

> **Você não faz isso sozinho.**

---

## 2. Senta com a galera de hardware  de verdade

Essa é a etapa mais importante de todo o processo, e a mais
subestimada por quem está começando.

Você precisa sentar com os membros de hardware e ter conversas
longas, às vezes repetitivas, às vezes frustrantes, e
absolutamente necessárias. Não é reunião formal com pauta.
É uma mesa bagunçada com componentes espalhados, um papel no
meio e muita gente falando ao mesmo tempo.

O tipo de pergunta que precisa ser respondida antes de qualquer
linha no CAD:

### Sobre cada componente

- Qual motor vamos usar? Por quê esse e não outro?
- Esse motor é grande demais para o espaço disponível?
- Onde fica o driver de motor? Ele precisa de ventilação?
- A bateria é pesada  onde ela vai para não deslocar o centro de massa?
- O microcontrolador precisa de acesso físico para programar durante
  a competição?
- Os sensores precisam estar a quantos milímetros do chão?
- Tem cabo saindo desse componente? Para onde vai esse cabo?

### Sobre o robô como sistema

- Qual o envelope máximo? (dimensões máximas pela regra da categoria)
- Quanto pesa tudo junto? Já pesamos cada componente?
- Se um parafuso soltar em competição, conseguimos reapertar
  sem desmontar tudo?
- Se o motor queimar, conseguimos trocar em menos de 10 minutos?

> Essas perguntas parecem chatas agora.
> Elas vão parecer geniais quando você estiver em competição
> com 5 minutos para consertar o robô.

---

## 3. A linguagem entre mecânica e hardware

Quando você senta com a galera de hardware, você vai perceber
que vocês falam línguas diferentes. Seu trabalho como mecânica
é fazer a ponte.

| Hardware fala... | Mecânica precisa entender... |
| :--- | :--- |
| "Esse motor puxa 2A no pico" | Aquecimento → precisa de espaço ao redor |
| "O encoder fica na traseira do motor" | +15mm no comprimento total |
| "A antena não pode ficar perto do motor" | Separação mínima no layout |
| "Precisa resetar o Arduino na largada" | Botão acessível por fora do chassi |
| "A bateria é LiPo, não pode deformar" | Suporte rígido, sem pressão lateral |

Cada restrição de hardware é uma **restrição geométrica** para você.
Anota todas. Elas viram cotas no CAD.

---

## 4. O insumo que você precisa sair da conversa

Antes de abrir o CAD, você precisa ter em mãos:

### Lista de componentes com dimensões

Para cada componente, você precisa do datasheet ou da medição física com paquímetro:

**Componente: Motor N20**  
Dimensões: Ø12mm × 25mm (corpo) + 9,5mm (eixo)  
Fixação: 2× parafuso M2, distância entre furos: 7mm  
Observação: gera vibração, evitar colar direto na PCB sensível

**Componente: Arduino Uno**  
Dimensões: 68,6mm × 53,4mm × 14mm (altura com conectores)  
Fixação: 4× furo M3, nos cantos  
Observação: porta USB precisa ficar acessível

**Componente: Bateria LiPo 7,4V 1000mAh**  
Dimensões: 60mm × 35mm × 12mm  
Fixação: velcro + trava lateral (não apertar)  
Observação: não perfurar, não dobrar, longe de superfícies quentes

Faz isso para **todos** os componentes. É trabalhoso uma vez,  
e salva horas de retrabalho no CAD depois.

### Restrições funcionais como cotas

Transforma cada restrição de hardware em uma dimensão ou distância:

**Sensores infravermelhos:** 8mm a 12mm do chão  
**Espaço entre motor e lateral do chassi:** mínimo 3mm  
**Botão de reset:** acessível externamente, max 20mm de profundidade  
**Conector de carga:** lateral direita, sem obstrução

---

## 5. Agora sim: começa o projeto

Com os componentes mapeados e as restrições levantadas, você
tem o que precisa para abrir o CAD com intenção.

O fluxo a partir daqui:

```
conversa com hardware
    ↓
lista de componentes + restrições
    ↓
croqui do layout (onde cada coisa fica)
    ↓
esboço com cotas
    ↓
CAD
    ↓
revisão com hardware ("isso aqui funciona?")
    ↓
ajuste
    ↓
fabricação
    ↓
montagem real
    ↓
tudo que estava errado aparece agora
    ↓
próxima versão
```

Percebe que revisão, ajuste e erro fazem parte do fluxo?  
Não são falhas do processo  são o processo.

---

## 6. Sobre errar (e por que você vai errar bastante)

Nenhum robô fica certo na primeira versão. Nenhum.

Os erros mais comuns na primeira montagem real:

- **O furo ficou deslocado 1mm**  o componente não encaixa.
  Solução: lima, reimprime, ou adapta. Aprende a tolerância certa
  para a próxima peça.

- **O cabo não tem comprimento suficiente**  o robô não fecha.
  Solução: roteamento diferente. Aprende a considerar caminho de
  cabo no CAD, não só ponto de origem e destino.

- **A peça impressa quebrou no primeiro teste**  espessura insuficiente.
  Solução: reimprime com mais material. Aprende onde colocar nervuras
  e onde o esforço realmente aparece.

- **O parafuso não passa**  furo muito apertado para impressão 3D.
  Solução: abre com broca ou reimprime com folga. Aprende que
  impressão 3D precisa de +0,2mm a +0,4mm de folga em furos.

- **O robô vibra demais**  motor sem amortecimento.
  Solução: borracha entre motor e chassi. Aprende que rigidez
  total nem sempre é a melhor opção.

> Cada um desses erros é uma habilidade que você não vai mais esquecer.
> Um engenheiro experiente não é alguém que nunca erra 
> é alguém que já errou o suficiente para saber o que vai dar errado
> antes de acontecer.

---

## 7. Checklist antes de mandar fabricar

Antes de imprimir ou cortar qualquer peça:

**Com o hardware:**
- [ ] Todos os componentes foram medidos com paquímetro
- [ ] Restrições funcionais foram convertidas em cotas
- [ ] Revisão do CAD foi feita com pelo menos um membro de hardware
- [ ] Alguém perguntou "como a gente manutém isso?"

**No CAD:**
- [ ] Todos os furos têm folga de montagem (+0,2mm para parafuso,
      +0,4mm para encaixe)
- [ ] Espessuras mínimas respeitadas (≥2mm para PLA estrutural)
- [ ] Cabo tem caminho definido, não só ponto de conexão
- [ ] Peça cabe dentro do envelope da categoria

**Antes da primeira montagem:**
- [ ] Todos os componentes estão em mãos
- [ ] Ferramentas necessárias estão disponíveis
- [ ] Alguém documentou o estado atual (foto do CAD, versão salva)

---

## 8. Uma última coisa

Quando o robô rodar pela primeira vez  mesmo que torto, mesmo
que lento, mesmo que por 3 segundos antes de travar  isso é
resultado direto de horas de conversa, de medidas, de croquis
e de peças que não encaixaram na primeira vez.

Guarda essa sensação. É ela que faz a equipe querer fazer
a versão dois.

---

*Anterior: [02  Escalas e Referências](./02-escalas-e-referencias.md)*  
*Próximo: [04  Regras e Dimensões](./04-regras-dimensoes.md)*