# Miniguia de Estudos: Arquitetura RAG e IAs Grounded com NotebookLM

> **Projeto desenvolvido para o Desafio de Aprendizagem Ativa da DIO (Digital Innovation One).**
> Um guia prático documentando a curadoria de fontes, testes de prompts e consolidação de conhecimento utilizando o NotebookLM da Google.

---

##  Contexto e Objetivos

### Contexto
O ecossistema de Inteligência Artificial evoluiu rapidamente para modelos baseados em **Retrieval-Augmented Generation (RAG)**, onde a IA responde com base exclusiva em fontes delimitadas de informação. Compreender como alimentar, testar e extrair dados estruturados dessas ferramentas é fundamental para desenvolvedores e profissionais de tecnologia.

### Objetivos de Estudo
1. **Curadoria Prática:** Selecionar artigos e documentações técnicas confiáveis sobre RAG e fine-tuning.
2. **Engenharia de Prompts:** Testar a capacidade de síntese do NotebookLM e registrar os limites/desafios da IA (troubleshooting).
3. **Consolidação do Conhecimento:** Gerar um miniguia de consulta rápida contendo resumos, glossário e prompts reutilizáveis para estudos futuros.

---

##  Curadoria de Fontes

Para alimentar o caderno no NotebookLM, foram selecionadas 4 fontes abertas (artigos técnicos e documentações):

1. **[What is RAG? - AWS Documentation](https://aws.amazon.com/pt/what-is/retrieved-augmented-generation/)**  
   *Foco:* Conceitos fundamentais de RAG, vetores de busca e integração com LLMs.
2. **[NotebookLM: Google's AI-Powered Notebook](https://notebooklm.google.com/)**  
   *Foco:* Documentação funcional da ferramenta e melhores práticas de ancoragem (*grounding*).
3. **[RAG vs Fine-Tuning - DeepLearning.AI Articles](https://www.deeplearning.ai/)**  
   *Foco:* Análise comparativa entre atualização de pesos do modelo vs. injeção de contexto em tempo de execução.
4. **[OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)**  
   *Foco:* Segurança, vazamento de dados de contexto e injeção de prompts em sistemas baseados em documentos.

---

## 🧪 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Nesta seção estão registradas as iterações de prompts testadas durante o estudo no NotebookLM, destacando os ajustes necessários para obter respostas precisas.

### Iteração 1: Pergunta Geral vs. Pergunta Delimitada
* **Prompt Inicial (Ingênuo):**  
  `"O que é RAG e como funciona?"`
* **Resultado Obtido:**  
  Resposta genérica citando conceitos de IA sem se prender totalmente aos detalhes técnicos dos documentos anexados.
* **Prompt Otimizado (Estratégico):**  
  `"Com base exclusivamente nas fontes anexadas, explique a diferença entre RAG e Fine-Tuning em 3 tópicos diretos. Inclua citações diretas quando possível."`
* **Resultado Obtido:**  
  A IA delimitou a resposta estritamente aos textos carregados, gerando uma tabela comparativa exata sem alucinações.

###  "Cicatrizes" e Aprendizados de Troubleshooting

| Desafio Encontrado | Causa Raiz | Solução Aplicada |
| :--- | :--- | :--- |
| Respostas vagando fora do escopo | O prompt dava margem para o conhecimento geral da LLM. | Forçar a diretiva *"Use apenas os documentos fornecidos"* no início do prompt. |
| Perda de contexto em perguntas longas | Solicitações com múltiplos comandos confusos. | Quebrar o prompt em etapas (primeiro resumo, depois extração de tabela, depois glossário). |
| Resumo muito genérico | Falta de formatação explícita na solicitação. | Especificar o output desejado (ex: *"Responda no formato Markdown com listas e negrito"*). |

---

##  Miniguia de Estudo (Entrega Final)

### 1. Resumo Estruturado do Conteúdo

* **O que é RAG:** Técnica que conecta um Modelo de Linguagem (LLM) a fontes de dados externas para recuperar informações atualizadas antes de gerar uma resposta.
* **Por que utilizar:** Reduz alucinações, permite manter a privacidade dos dados e evita o custo elevado de treinar novamente um modelo do zero.
* **Fluxo de Funcionamento:**
  1. *Ingestão:* Documentos são convertidos em vetores (*embeddings*).
  2. *Busca:* A pergunta do usuário busca os trechos mais relevantes no banco vetorial.
  3. *Geração:* A IA lê a pergunta + trechos recuperados e gera a resposta fundamentada.

### 2. Glossário Técnico

* **Grounding (Ancoragem):** Processo de restringir as respostas do modelo estritamente a um conjunto de dados ou documentos fornecidos.
* **Embeddings:** Representação numérica (vetorial) de textos que permite à IA medir a similaridade semântica entre termos.
* **Hallucination (Alucinação):** Quando o modelo gera informações convincentes, porém falsas ou não sustentadas pelas fontes.
* **Prompt Injection:** Risco de segurança onde comandos maliciosos dentro dos documentos tentam alterar o comportamento da IA.

### 3. Prompts Reutilizáveis para Revisões Futuras

```markdown
# Biblioteca de Prompts para o NotebookLM

## Prompt 1: Extração de Conceitos Chave
"A partir dos documentos anexados, liste os 5 principais conceitos técnicos abordados e crie uma definição de uma frase para cada um."

## Prompt 2: Simulado de Fixação
"Crie 3 perguntas no formato múltipla escolha baseadas nas fontes. Não forneça as respostas imediatamente; aguarde eu responder para corrigir."

## Prompt 3: Resumo Executivo
"Sintetize os pontos principais deste caderno em um texto de até 200 palavras, estruturado em parágrafos curtos com tópicos em negrito."
