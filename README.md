#  Miniguia de Estudos: Educação Financeira e Finanças Pessoais com NotebookLM

> **Projeto desenvolvido para o Desafio de Aprendizagem Ativa da DIO (Digital Innovation One).**  
> Um caderno temático construído no NotebookLM da Google para organizar conceitos de orçamento, reserva de emergência e planejamento financeiro introdutório.

---

##  Contexto e Objetivos

### Contexto
A educação financeira é essencial para tomada de decisões conscientes sobre orçamento, controle de endividamento e construção de patrimônio. Este projeto utiliza o **NotebookLM** como ferramenta de aprendizagem ativa, realizando curadoria de fontes oficiais e aplicando engenharia de prompts para transformar leituras em conhecimento estruturado.

### Objetivos de Estudo
1. **Compreensão de Base:** Dominar conceitos introdutórios como Reserva de Emergência, Regra 50-30-20 e Taxa Selic/Inflação.
2. **Aprendizagem Ativa com IA:** Utilizar o NotebookLM para sintetizar e cruzar informações das fontes sem alucinações.
3. **Documentação Prática:** Registrar o processo de refinamento de perguntas (troubleshooting) e criar um guia reutilizável de revisão.

---

##  Curadoria de Fontes

Para alimentar o caderno no NotebookLM, foram selecionadas 4 fontes abertas e confiáveis:

1. **[Caderno de Educação Financeira - Banco Central do Brasil](https://www.bcb.gov.br/)**  
   *Foco:* Conceitos formais de planejamento, orçamento familiar e uso consciente do crédito.
2. **[Guia de Proteção ao Investidor - CVM](https://www.investidor.gov.br/)**  
   *Foco:* Perfis de investimento, risco vs. retorno e fundamentos de renda fixa.
3. **[Guia Prático da Reserva de Emergência - ANBIMA](https://www.anbima.com.br/)**  
   *Foco:* Liquidez, rentabilidade básica e onde alocar a reserva.
4. **[Metodologias de Orçamento Pessoal (Regra 50-30-20)](https://www.serasa.com.br/)**  
   *Foco:* Divisão prática de renda entre necessidades, desejos e investimentos.

---

##  Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Abaixo estão registrados os testes de prompts realizados durante as consultas ao NotebookLM:

### Iteração 1: Pergunta Geral vs. Pergunta Delimitada
* **Prompt Vago (Inicial):**  
  `"Como eu faço para juntar dinheiro?"`
* **Resposta Obtida:** Dicas genéricas de internet, sem grounding e sem profundidade.
* **Prompt Otimizado (Estratégico):**  
  `"Com base exclusivamente nas fontes do Banco Central e CVM anexadas, explique o passo a passo para calcular e estruturar uma Reserva de Emergência para um profissional assalariado. Apresente em formato de tópicos."`
* **Resposta Obtida:** A IA citou exatamente os prazos de cobertura (3 a 6 meses de custo de vida) e apontou os produtos de renda fixa com liquidez diária citados nos manuais.

### "Cicatrizes" e Aprendizados de Troubleshooting

| Dificuldade Encontrada | Causa | Solução Aplicada |
| :--- | :--- | :--- |
| MISTURA DE CONCEITOS: A IA misturou reserva com investimentos de alto risco. | Prompt não delimitava o objetivo de segurança e liquidez. | Adicionou-se a restrição: *"Considere apenas opções de baixa volatilidade e alta liquidez mencionadas nos PDFs"*. |
| RESPOSTAS LONGAS: Textos extensos e difíceis de revisar rápido. | Falta de formatação explícita. | Foi exigido o formato de **tabela** e **listas com marcadores**. |

---

## 📖 Miniguia de Estudo (Entrega Final)

### 1. Resumo Estruturado do Conteúdo

* **Orçamento Consciente (Regra 50-30-20):**  
  * **50% Necessidades:** Gastos essenciais (moradia, alimentação básica, saúde, transporte).
  * **30% Desejos Pessoais:** Lazer, estilo de vida, assinaturas.
  * **20% Prioridades Financeiras:** Quitação de dívidas ou investimentos/reserva.
* **Reserva de Emergência:**  
  * Montante correspondente a **3 a 6 meses do custo de vida mensal**.
  * Deve estar alocada em aplicações com **liquidez imediata (diária)** e **baixo risco** (ex: Tesouro Selic, CDB 100% CDI com resgate diário).

### 2. Glossário de Conceitos Básicos

* **Liquidez:** A facilidade e rapidez com que um ativo/investimento pode ser convertido em dinheiro disponível sem perda relevante de valor.
* **CDI (Certificado de Depósito Interbancário):** Taxa de juros sintética que baliza a rentabilidade de grande parte dos investimentos de renda fixa.
* **Inflação (IPCA):** A taxa de variação dos preços de bens e serviços. Investimentos precisam render acima dela para garantir ganho real.
* **Taxa Selic:** A taxa básica de juros da economia brasileira, definida pelo Banco Central.

### 3. Biblioteca de Prompts Reutilizáveis

```markdown
#  Prompts para Revisão do Caderno Financeiro

## Prompt 1: Simulação de Caso Prático
"Com base nos materiais de finanças, atue como um educador financeiro. Tenho uma renda mensal de X e custos fixos de Y. Como devo organizar meus aportes segundo as fontes?"

## Prompt 2: Comparador de Conceitos
"Crie uma tabela comparativa resumindo as diferenças entre Poupança, Tesouro Selic e CDB de liquidez diária com base apenas no material carregado."

## Prompt 3: Questionário de Fixação
"Gere 5 perguntas de múltipla escolha sobre o conteúdo de educação financeira para eu testar meu aprendizado. Mostre o gabarito apenas no final."
