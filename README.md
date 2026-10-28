# **Políticas de Crédito e Precificação Baseada em Risco**

## Contexto de Negócio

O **Lending Club** é uma plataforma de empréstimos (P2P) fundada em 2007 nos Estados Unidos, atuando como intermediária entre tomadores de crédito (pessoas físicas) e investidores individuais ou institucionais. Os empréstimos concedidos abrangem diversas finalidades, como consolidação de dívidas, reformas residenciais, financiamento de veículos e despesas médicas.

Em operações de crédito ao consumidor, o principal desafio de negócio não se resume a classificar binariamente quem irá atrasar, mas sim **estimar probabilidades calibradas de inadimplência** no momento da solicitação para quantificar a **Perda Esperada** e definir uma **Política de Crédito e Precificação (*Risk-Based Pricing*)** financeiramente sustentável.

## Objetivo do Projeto

Construir uma solução analítica com foco em explicabilidade e tomada de decisão:

1. **Estimar a Probabilidade de Default (PD)** para solicitações de empréstimo utilizando exclusivamente variáveis disponíveis no momento da concessão (prevenção estrita de *data leakage* temporal e pós-concessão)
2. **Avaliar a qualidade probabilística** do modelo em regime *Out-of-Time*, tendo o **Log Loss** e o **Brier Score** como métricas primárias de calibração
3. **Propor uma Política de Crédito baseada em Perda Esperada**, combinando a probabilidade predita pelo modelo ($\text{PD}$) com estimativas empíricas de exposição ($\text{EAD}$) e severidade da perda ($\text{LGD}$):

$$\text{Expected Loss}(x) = \text{PD}(x) \times \text{EAD}(x) \times \text{LGD}(x)$$
