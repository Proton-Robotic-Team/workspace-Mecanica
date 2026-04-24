# 02  Escalas e Referências

> **Objetivo:** Aprender a estimar as dimensões de um robô a partir de
> imagens e datasheets e entender quando isso é suficiente e quando não é.

---

## 1. Por que isso importa?

Antes de projetar qualquer robô, você vai pesquisar o que já existe.
O problema é que a internet não te entrega um CAD com cotas  ela te
entrega fotos, vídeos e specs incompletas.

A habilidade de **extrair dimensões de uma imagem** é o que separa quem
consegue aprender com robôs de outras equipes de quem só consegue copiar.

---

## 2. O fluxo completo: do vídeo ao croqui

```
YouTube/imagem  →  referência conhecida  →  datasheet  →  escala  →  croqui
(foto do robô)      (motor, roda, placa)    (medida real) (cálculo)  (dimensões)
```

Parece trabalhoso, mas na prática leva menos de 20 minutos quando você
já sabe o que está fazendo.

---

## 3. Passo a passo: engenharia reversa por imagem

### Passo 1  Ache uma boa imagem

No YouTube, procure o robô que quer estudar e pause em um momento onde:
- O robô está em **vista lateral ou frontal** (de frente, de lado, de cima)
- Está **parado**, sem motion blur
- A câmera está **paralela ao robô** (sem perspectiva exagerada)
- Dá pra ver **pelo menos um componente que você reconhece**

> 💡 Busca: `"seguidor de linha competição [ano]"` ou
> `"line follower robot"` no YouTube.
> Canais de competição como OBR, LARC e RoboCore têm ótimas filmagens.

Tira um print e salva.

---

### Passo 2  Identifique sua referência

Dentro da imagem, procura um componente que você conhece e que tem
**datasheet com dimensões**.

Componentes ideais para referência:

| Componente | Por que é bom de referência |
| :--- | :--- |
| **Motor N20** | Diâmetro fixo de 12mm, todo mundo usa |
| **Arduino Uno** | PCB de 68,6mm × 53,4mm, muito comum |
| **Servo MG995** | Corpo de 40,7mm × 19,7mm × 42,9mm |
| **Roda de borracha** | Diâmetro geralmente 40mm, 60mm ou 65mm |
| **Parafuso M3** | Cabeça de ~5,5mm de diâmetro |

Escolhe o componente que aparece com **mais clareza e de frente** na imagem.

---

### Passo 3  Busca o datasheet

Com o nome do componente em mãos, busca o datasheet:

Google: "motor N20 datasheet dimensions"
Google: "Arduino Uno R3 dimensions PDF"
Google: "MG995 servo dimensions datasheet"

O que você precisa do datasheet é **uma dimensão absoluta**  comprimento,
largura ou diâmetro. Anota o valor em mm.

> Exemplo: Motor N20 → Diâmetro do corpo: **12mm**, Comprimento total: **25mm**

---

### Passo 4  Meça na imagem e calcule a escala

Abre a imagem no computador. Usa qualquer ferramenta de medição:

- **Paint (Windows):** barra de status mostra coordenadas do cursor em pixels
- **Preview (Mac):** ferramentas → mostrar marcação → régua
- **GIMP ou Photopea:** `Ferramentas → Medição`
- **No próprio browser:** inspeciona a imagem e usa a régua do DevTools

Mede a dimensão **do componente de referência** na imagem, em pixels.

Depois aplica a regra de 3:

```
escala = medida_real_mm / medida_na_imagem_px
dimensão_real = dimensão_na_imagem_px × escala
```

#### Exemplo prático

Você tira um print de um seguidor de linha.  
O motor N20 aparece na imagem com **47 pixels** de comprimento.  
O datasheet diz que o comprimento real é **25mm**.

```
escala = 25mm / 47px = 0,532 mm/px
O chassi mede 210px na imagem.
Dimensão estimada = 210px × 0,532 = ~111mm
```

> ⚠️ **Isso é uma estimativa, não uma medida.**  
> O erro típico é de 5% a 15% dependendo da qualidade da imagem e da
> distorção da câmera. Use como ponto de partida, não como dado final.

---

### Passo 5  Valide com uma segunda referência

Nunca confie em uma única referência. Se a imagem tem dois componentes
conhecidos, mede os dois e compara as escalas calculadas.

Se as escalas baterem (diferença < 10%), você está no caminho certo.
Se divergirem muito, a imagem provavelmente tem perspectiva ou distorção.

---

## 4. Validando com uma régua comum

Quando você tem **o componente físico na mão** e a imagem na tela, dá pra
fazer ainda mais rápido:

1. Imprime a imagem em escala conhecida (ex: A4 inteiro)
2. Mede o componente na foto impressa com a régua
3. Mede o componente real com o paquímetro
4. Calcula a escala da impressão
5. Mede as outras partes do robô impresso e multiplica pela escala

É menos preciso que o método digital, mas funciona quando você está
longe do computador ou quer uma estimativa rápida em campo.

---

## 5. O atalho: arquivos 3D prontos

Antes de fazer engenharia reversa, sempre vale procurar se alguém já
modelou o robô ou os componentes:

| Onde procurar | O que você acha |
| :--- | :--- |
| **GrabCAD** (grabcad.com) | Modelos técnicos de alta qualidade |
| **Thingiverse** (thingiverse.com) | Peças para impressão 3D, chassi de robôs |
| **Printables** (printables.com) | Alternativa ao Thingiverse, boa qualidade |
| **GitHub** | Equipes que abriram o projeto completo com CAD |
| **OnShape** (público) | Modelos diretamente no browser, sem download |

Busca: `"line follower robot" site:grabcad.com` ou  
`"seguidor de linha" site:thingiverse.com`

### O que você ganha e o que você perde

| | Arquivo 3D pronto | Engenharia reversa |
| :--- | :-: | :-: |
| **Velocidade** | ✅ Imediato | ❌ Leva tempo |
| **Precisão** | ✅ Exata | ⚠️ Estimada |
| **Aprendizado** | ❌ Você não entende o porquê | ✅ Você entende cada decisão |
| **Disponibilidade** | ❌ Nem sempre existe | ✅ Sempre dá pra tentar |

> 💡 **Recomendação da equipe:** use o arquivo 3D para validar sua  
> engenharia reversa. Se você estimou 111mm e o modelo diz 108mm, você  
> está aprendendo a calibrar seu olho. Se você pula direto pro arquivo  
> 3D, você não desenvolve esse senso.

---

## 6. Erros clássicos nesse processo

- **Usar imagem com perspectiva:** câmera em diagonal distorce tudo.
  Só usa imagens onde o robô está exatamente de frente ou de lado.

- **Usar a mesma referência pra tudo:** meça pelo menos dois componentes
  diferentes e cruze os resultados.

- **Ignorar a distorção de lente:** câmeras wide-angle (como GoPro)
  distorcem muito as bordas. Prefere imagens com zoom neutro.

- **Confiar no tamanho do thumbnail:** o YouTube comprime e recorta as
  thumbnails. Sempre tira o print do próprio vídeo pausado.

- **Não anotar de onde veio a imagem:** sempre salva a URL junto com o
  print. Meses depois você vai querer rever o vídeo original.

---

## 7. Template de anotação

Quando você fizer esse processo, anota assim:

```
Robô analisado:         [nome / equipe / competição]
Fonte:                  [URL do vídeo ou imagem]
Data:                   [dd/mm/aaaa]

Componente de referência: Motor N20
Medida na imagem:       47px
Medida real (datasheet):  25mm
Escala calculada:       0,532 mm/px

Segunda referência:     Arduino Uno (largura)
Medida na imagem:       101px
Medida real (datasheet):  53,4mm
Escala calculada:       0,529 mm/px
→ Escalas batem ✅

Dimensões estimadas do robô:
Comprimento:            ___mm
Largura:                ___mm
Altura:                 ___mm

Observações:            [perspectiva, qualidade da imagem, etc.]
```

---

*Anterior: [01  Desenho Técnico](./01-desenho-tecnico.md)*  
*Próximo: [03  Montagem e Hardware](./03-montagem-hardware.md)*