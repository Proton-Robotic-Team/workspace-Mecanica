# 01  Desenho Técnico

> **Objetivo:** Sair daqui sabendo ler uma medida, fazer um croqui à mão e
> entender como esse croqui vira um projeto no CAD.

---

## 1. Por que isso importa na equipe?

Antes de modelar qualquer peça no CAD, você precisa saber:
- Qual a medida real de um componente que você tem na mão
- Como anotar isso de forma que outra pessoa entenda
- Como transformar um rascunho em algo fabricável

Esse fluxo  **esboço → medir → croqui → CAD**  é o ciclo básico de
qualquer peça que fazemos.

---

## 2. Metrologia: medindo com paquímetro

Paquímetro é a única ferramenta de medição de precisão que usamos.
Com ele dá pra fazer 4 tipos de medição:

| Medição | Onde usar no robô |
| :--- | :--- |
| **Externa** | Diâmetro de eixos, largura de perfis |
| **Interna** | Diâmetro de furos, encaixes |
| **Profundidade** | Profundidade de rebaixos |
| **Ressalto** | Degraus entre superfícies |

### Vídeos de referência

Assista nessa ordem:

1. 📺 **[Telecurso 2000  Metrologia: Paquímetro](https://www.youtube.com/watch?v=-h78uZk-1Cw&list=PLgy1AhY2-u_SwDnfl4hECxflx15SRBCaV&index=4)**  
   O clássico. Explica os tipos de escala (1/10, 1/20, 1/50) com calma.  
   Assiste pelo menos até o exercício resolvido.

2. 📺 **[4 Maneiras](https://www.youtube.com/shorts/8wLHbyYhEos)**  
   Mais rápido, mostra as 4 medições na prática.

### Erros mais comuns com paquímetro

- **Apertar demais:** deforma peças plásticas e dá leitura errada
- **Ler a escala errada:** confirma se seu paquímetro é 1/10 ou 1/20
  antes de ler o nônio
- **Medir no lugar errado:** em eixos, mede no centro, não na ponta
- **Não zerar antes:** sempre fecha o paquímetro e confirma que marca 0

---

## 3. Do objeto ao papel: o Croqui

Croqui é um desenho **à mão livre**, sem escala, sem régua.  
O objetivo não é ser bonito  é **capturar as informações** antes de esquecer.

### O que um bom croqui tem

**Regras práticas:**
- Anota TODAS as medidas que você tirou com o paquímetro
- Usa `Ø` antes de diâmetros
- Indica o material e para que serve a peça
- Não precisa de escala, mas proporcione visualmente
  (se um lado é o dobro do outro, desenha o dobro)

---

## 4. Do Esboço ao Croqui

Croqui é a versão **organizada** do Esboço, ainda no papel mas já com
intenção de ser entendido por outra pessoa.

A diferença principal:

| | Esboço | Croqui |
| :--- | :--- | :--- |
| **Ferramenta** | Qualquer papel, caneta | Papel quadriculado, lapiseira |
| **Escala** | Não tem | Aproximada (ex: 1:1 ou 1:2) |
| **Vistas** | Uma ou duas | Frontal + lateral + superior |
| **Cotas** | Anotadas à mão | Organizadas com linha de cota |

### As 3 vistas que sempre usamos

- **Frontal:** o que você vê de frente
- **Lateral:** o que você vê do lado direito
- **Superior:** o que você vê de cima

> 💡 Para a maioria das peças do robô, frontal + superior já resolvem.
> Adiciona lateral só quando tem detalhe que não aparece nas outras duas.

---

## 5. Do Esboço ao CAD

Com o esboço em mãos, a modelagem no CAD segue sempre o mesmo fluxo:

### Fluxo prático

1. **Escolhe o plano**  na maioria das peças, começa pela vista frontal
2. **Faz o sketch**  desenha o contorno 2D usando as cotas do esboço
3. **Extruda**  dá profundidade para a peça (usa a cota da vista lateral)
4. **Adiciona furos e detalhes**  cada furo é um novo sketch + operação
5. **Valida**  compara com o esboço, confere se as medidas batem

### Do papel para o CAD: exemplo

> O documento de CAD tem o passo a passo dentro do software.
> Aqui o importante é entender o **fluxo**, não os cliques.

---

## 6. Checklist antes de ir ao CAD

Antes de abrir o software, confirma:

- [ ] Todas as medidas externas foram tiradas com paquímetro
- [ ] Diâmetros de furo anotados com `Ø`
- [ ] Esboço tem as 3 vistas necessárias (ou justificativa para menos)
- [ ] Material definido
- [ ] Você sabe para onde essa peça vai no robô e o que ela toca

---

*Próximo: [02  Escalas e Referências](./02-escalas-e-referencias.md)*