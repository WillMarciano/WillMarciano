# 🤖 Guia de Comandos IA - Master Template

Este guia descreve os comandos customizados configurados para otimizar o fluxo de desenvolvimento, gestão de sprints e auditoria técnica em qualquer projeto que utilize o **Master Template**.

---

## 🚀 1. Gestão e Planejamento (PM/PO)
Comandos para manter a IA alinhada com o cronograma e a documentação do projeto.

| Comando | O que faz | Contexto de Uso |
| :--- | :--- | :--- |
| **`Bora`** | Atua como Product Manager. Lê o arquivo de Sprints e define a próxima tarefa técnica pendente. | Início de jornada ou troca de tarefa. |
| **`Entender_escopo`** | Sincroniza a IA com os documentos de requisitos e sprints antes de iniciar qualquer código. | Início de uma nova funcionalidade. |
| **`Refinamento_itens`** | Automatiza o ciclo de vida da Sprint: arquiva o que está 100% e prepara a próxima. Lista o que impede o fechamento da atual. | Final de Sprint ou Planejamento. |
| **`Update_docs`** | Atualiza a documentação técnica do serviço/componente atual com base no código real. | Pós-implementação. |
| **`Update_all_docs`** | Gera um checklist de quais arquivos de documentação ficaram obsoletos após as mudanças. | Antes de realizar um Merge/Pull Request. |

---

## 🛠️ 2. Desenvolvimento e Produtividade (Dev)
Comandos operacionais para acelerar a escrita de código seguindo padrões de excelência.

| Comando | O que faz | Contexto de Uso |
| :--- | :--- | :--- |
| **`Scaffold_feature`** | Gera toda a estrutura básica (boilerplates) de uma nova funcionalidade seguindo a arquitetura do projeto. | Criação de novos módulos ou endpoints. |
| **`Espelhar_padrao`** | Copia o estilo de implementação, injeção de dependência e mocks de um arquivo de referência para um novo. | Manutenção de consistência visual e técnica. |
| **`Gerar_teste`** | Cria suítes de testes unitários utilizando o framework definido no template (TDD mindset). | Escrita de novas lógicas de negócio. |
| **`Map_dto`** | Cria códigos de mapeamento entre modelos internos e objetos de transferência (DTOs). | Integração entre camadas de aplicação e API. |
| **`Refactor_this`** | Analisa o código selecionado em busca de "cheiros" (code smells) e sugere melhorias imediatas. | Refatoração de código legado ou complexo. |

---

## 🛡️ 3. Arquitetura e Governança (Tech Lead / QA)
Comandos de auditoria rigorosa para garantir que nenhum débito técnico passe despercebido.

| Comando | O que faz | Contexto de Uso |
| :--- | :--- | :--- |
| **`TL_Review`** | **Veredito Binário (GO/NO-GO)**. Faz uma auditoria completa de documentação, padrões de código e segurança. | Code Review oficial. |
| **`Verificar_cobertura`** | Executa as ferramentas de cobertura e apresenta um "Raio-X" das classes menos testadas. | Auditoria de Qualidade. |
| **`Validar_mensageria`** | Verifica a resiliência em fluxos de eventos, transações de banco e padrões de integração. | Implementação de Sagas, Outbox ou RabbitMQ. |
| **`Gerar_diagrama`** | Transforma a lógica do código em diagramas Mermaid formatados para não quebrar em PDFs. | Documentação de fluxos complexos. |
| **`Revisar_contrato`** | Valida se a API está expondo apenas o necessário e se o Swagger/Docs estão corretos. | Revisão de interfaces externas. |
| **`Valida_build`** | Relatório executivo final combinando auditoria técnica, segurança e documentação. | O "Portão de Saída" antes do deploy. |

---

## 💡 4. Como Calibrar este Guia
Para usar este guia em um novo projeto:
1.  **Defina a Stack:** No arquivo de instruções, substitua os placeholders `[FRAMEWORK_TESTES]` e `[LINGUAGEM]`.
2.  **Mapeie os Caminhos:** Certifique-se de que os comandos `Bora` e `Refinamento_itens` apontam para as pastas reais do seu repositório.
3.  **Tolerância Zero:** A IA está configurada para não aceitar código sem documentação XML (em inglês) e sem testes. Mantenha o rigor!

---
#### 📝 Controle de Versão do Template
- **Versão:** 1.0 (Universal)
- **Status:** Homologado para Multi-Linguagem
