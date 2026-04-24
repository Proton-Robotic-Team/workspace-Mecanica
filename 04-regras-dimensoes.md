# 04  Regras e Dimensões

> **Objetivo:** Entender como as regras de competição definem seus
> limites de projeto  e como verificar se o seu robô está dentro deles.

---

## 1. As regras são o seu primeiro requisito de engenharia

Antes de qualquer croqui, antes de qualquer conversa com hardware,
as regras da categoria já definiram boa parte do seu projeto.

Dimensão máxima, peso máximo, formato da arena, altura da pista 
tudo isso é restrição de projeto, não burocracia.

> Um robô tecnicamente brilhante que não passa na homologação
> não compete. Simples assim.

---

## 2. As categorias da equipe

Cada categoria tem suas próprias regras. Acesse pelo índice abaixo:

| Categoria | O que faz |
| :--- | :--- |
| [ArtBot](./ArtBot/) | Robô artístico, foco em movimento e apresentação |
| [Combate](./Combate/) | Robô de batalha, destrói ou imobiliza o adversário |
| [Futebol](./Futebol/) | Robô joga futebol em arena padronizada |
| [Hockey](./Hockey/) | Variação do futebol com disco em vez de bola |
| [Micromouse](./Micromouse/) | Resolve labirinto de forma autônoma |
| [Seguidor de Linha](./Seguidor%20de%20Linha/) | Percorre pista seguindo uma linha |
| [Sumô](./Sumo/) | Empurra o adversário para fora da arena |
| [Trekking](./Trekking/) | Navegação autônoma por terreno com obstáculos |

> Os documentos de cada categoria ficam nas subpastas acima.  
> Este documento aqui é o guia de **como ler e usar** essas regras.

---

## 3. O que sempre verificar em qualquer categoria

Independente da categoria, toda análise de regras passa pelos
mesmos pontos. Usa isso como roteiro:

### 3.1 Dimensões do robô

As regras definem o **envelope máximo**  o espaço que o robô
não pode ultrapassar.

Perguntas obrigatórias:
- As dimensões são medidas com o robô **parado ou em movimento**?
  (algumas categorias permitem expansão após a largada)
- A medição é com ou sem sensores externos, antenas, fios?
- Existe limite de **altura** separado de comprimento e largura?
- Para Sumô: o robô pode começar dobrado e expandir?

Exemplo de anotação:

```
Categoria:          Sumô Mini
Comprimento máx:    100mm
Largura máx:        100mm
Altura:             sem limite
Peso máx:           500g
Medição:            robô parado, antes da largada
```

### 3.2 Peso

- Qual o limite de peso?
- A pesagem é com ou sem bateria?
- Existe peso **mínimo** (menos comum, mas existe em algumas categorias)?

> Pesa cada componente individual com uma balança de precisão e
> mantém uma planilha de peso acumulado durante o projeto.
> Descobrir que está 50g acima na véspera da competição é tarde demais.

### 3.3 A arena ou pista

As dimensões do robô não fazem sentido sem entender o espaço
onde ele vai operar.

| O que verificar | Por que importa para mecânica |
| :--- | :--- |
| **Largura da pista** | Define o quanto o robô pode oscilar lateralmente |
| **Espessura da linha (seguidor)** | Define posicionamento dos sensores |
| **Altura da borda (sumô)** | Define altura mínima do sistema de ataque |
| **Tipo de superfície** | Define dureza das rodas e coeficiente de atrito |
| **Iluminação da arena** | Afeta sensores, pode exigir proteção física |
| **Dimensão da arena (combate/futebol)** | Define raio de atuação e estratégia de chassi |

### 3.4 Restrições de material e segurança

Algumas categorias proíbem materiais específicos:
- Combate: proibição de fluidos, gases, materiais que explodem
- Sumô: superfícies adesivas são geralmente proibidas
- Futebol: bordas cortantes proibidas

Lê essa seção das regras com atenção. É o tipo de coisa que
faz o robô ser desclassificado na inspeção sem nem competir.

---

## 4. Como ler um documento de regras

Documentos de regras de robótica costumam ser densos. Estratégia
de leitura que funciona:

**Primeira leitura  visão geral (5 min)**  
Lê tudo sem parar, sem anotar. Só para entender a estrutura.

**Segunda leitura  extrai os números (10 min)**  
Varre o documento procurando especificamente:
- Dimensões (mm, cm)
- Pesos (g, kg)
- Distâncias (altura do sensor, distância da linha)
- Materiais proibidos

Anota tudo em uma tabela simples. Esses são seus **requisitos de projeto**.

**Terceira leitura  entende as bordas (10 min)**  
Lê as seções de homologação e penalidades. Entende o que é
verificado antes da competição e como é verificado.

> 💡 Quando tiver dúvida sobre a interpretação de uma regra,  
> a resposta certa é **perguntar para o organizador**, não adivinhar.  
> Uma interpretação errada pode invalidar semanas de projeto.

---

## 5. Checklist de homologação

Usa isso antes de qualquer competição:

**Dimensões**
- [ ] Medido comprimento máximo (com paquímetro, não no CAD)
- [ ] Medido largura máxima
- [ ] Medido altura máxima (se aplicável)
- [ ] Verificado se sensores e cabos estão dentro do envelope

**Peso**
- [ ] Pesado o robô completo, com bateria carregada
- [ ] Dentro do limite da categoria

**Arena/Pista**
- [ ] Verificadas dimensões da pista ou arena que será usada
- [ ] Testado em superfície similar à da competição

**Segurança e material**
- [ ] Sem bordas cortantes expostas
- [ ] Sem materiais proibidos pela categoria
- [ ] Bateria segura e sem danos visíveis

**Documentação**
- [ ] Sabe o nome e versão do regulamento usado no projeto
- [ ] Tem o regulamento salvo offline (PDF)

---

## 6. Quando as regras mudam

Regulamentos são atualizados todo ano, às vezes no meio da temporada.

Boas práticas:
- Sempre baixa o regulamento direto do site oficial do organizador
- Anota a **versão e data** do regulamento no início do projeto
- Quando sair uma nova versão, compara com a anterior e verifica
  se algo que afeta o projeto mudou
- Nunca projeta baseado em regulamento de ano anterior sem confirmar

---

*Anterior: [03  Montagem e Hardware](./03-montagem-hardware.md)*  
*Próximo: [05  CAD](./05-cad.md)*