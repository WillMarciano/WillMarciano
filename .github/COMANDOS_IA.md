# 🤖 Guia de Comandos IA - Master Template

Este guia contém os comandos personalizados configurados para a IA em formato universal. O foco é manter a produtividade máxima com **Tolerância Zero** para violações de arquitetura e padrões da linguagem do projeto.

------------

## 🚀 1. Fluxo de Trabalho e Sprints (PM/PO)

| Comando | O que faz | Contexto de Uso | Exemplo no Chat |
| :--- | :--- | :--- | :--- |
| **`Bora`** | Lê o tracking de Sprints, acha a próxima tarefa pendente e cria um plano técnico. | Início de jornada ou puxada de tarefa. | `Bora` |
| **`Entender_escopo`** | Alinha a IA com os requisitos da funcionalidade, aguardando aprovação antes de codar. | Análise inicial de novos requisitos. | `Entender_escopo da funcionalidade X` |
| **`Refinamento_itens`** | Arquiva sprints concluídas, abre a próxima do backlog ou lista pendências. | Final de Sprint ou Planejamento (Planning). | `Refinamento_itens` |
| **`Update_docs`** | Lê o componente alterado e reescreve a documentação (blindando diagramas). | Logo após finalizar o código de um módulo. | `Update_docs para o módulo #Doc.md` |
| **`Update_all_docs`** | Varre o repositório/Git e gera checklist das documentações que ficaram desatualizadas. | Antes de abrir um Pull Request / Merge. | `Update_all_docs` |

------------

## 🛠️ 2. Desenvolvimento e Produtividade (Dev)

| Comando | O que faz | Contexto de Uso | Exemplo no Chat |
| :--- | :--- | :--- | :--- |
| **`Scaffold_feature`** | Gera o esqueleto completo seguindo a arquitetura base configurada no projeto. | Criação do zero de um novo fluxo. | `Scaffold_feature para Carrinho` |
| **`Espelhar_padrao`** | Clona o estilo de código (injeções, mocks, nomenclatura) de um arquivo base. | Manutenção de consistência no projeto. | `Espelhar_padrao de #A.ext para #B.ext` |
| **`Gerar_teste`** | Cria suíte de testes unitários usando o framework primário definido no padrão AAA. | Escrita de lógica de negócio e TDD. | `Gerar_teste para a classe #Servico.ext` |
| **`Map_dto`** | Gera código de mapeamento blindando os Modelos de Domínio para não vazarem na API. | Integração entre Core e Presentation. | `Map_dto entre #Modelo e #Response` |
| **`Refactor_this`** | Procura code smells e aplica a regra do escoteiro (limpar o que achar sujo). | Refatorando código legado ou sujo. | `Refactor_this selecionando o método` |
| **`Tunar_performance`** | Atua como DBA e Engenheiro de Performance. Caça gargalos de memória, problemas de N+1 no ORM, falta de paginação e sugere otimizações extremas. | Otimização de rotas lentas ou queries pesadas de relatórios. | `Tunar_performance neste repositório` |

------------

## 🏗️ 3. Arquitetura e Integrações (Architect)

| Comando | O que faz | Contexto de Uso | Exemplo no Chat |
| :--- | :--- | :--- | :--- |
| **`Planejar_infra`** | Lê arquivos (`package.json`, `.csproj`) mapeando dependências para calcular sizing. | Planejamento de capacidade e Cloud. | `Planejar_infra para 10k requisições/s` |
| **`Validar_mensageria`** | Verifica padrões de integração, sagas, transações em banco e cancelamentos. | Integração distribuída e eventos. | `Validar_mensageria no #Handler.ext` |
| **`Revisar_contrato`** | Valida Swagger/OpenAPI, DTOs e mapeamento de status HTTP. | Liberação de APIs para consumidores. | `Revisar_contrato da rota #Controller.ext` |
| **`Gerar_diagrama`** | Mapeia o fluxo do código e gera um Sequence Diagram Mermaid blindado. | Documentação viva para fluxos complexos. | `Gerar_diagrama do fluxo de pagamento` |
| **`Discovery_completo`** | Realiza engenharia reversa total em sistemas sem documentação. Analisa UI, Backend, Dependências e Infra para explicar o negócio e os fluxos. | Assunção de sistemas legados ou projetos sem handover. | `Discovery_completo do projeto` |
| **`Planejar_migracao`** | Cria a arquitetura *To-Be* de um sistema legado. Gera matriz De-Para, estratégia de corte (ex: Strangler Pattern) e estima tempo em Sprints/Semanas com base no tamanho do time. | Planejamento de refatoração ou reescrita total de aplicações antigas. | `Planejar_migracao para .NET Core e Angular com 3 Devs Sêniors` |
| **`Avaliar_rebuild`** | Resolve o dilema "Refatorar vs Reescrever". Avalia o débito técnico do legado e compara o custo/benefício de atualizar a base atual vs criar do zero. | Tomada de decisão orçamentária e técnica em sistemas muito defasados. | `Avaliar_rebuild deste app em .NET Framework 4` |

------------

## 🛡️ 4. Qualidade e Auditoria (Tech Lead / QA)

| Comando | O que faz | Contexto de Uso | Exemplo no Chat |
| :--- | :--- | :--- | :--- |
| **`Verificar_cobertura`**| Dispara o runner de testes local e gera um "Raio-X" ordenando as piores classes. | Auditoria contínua de qualidade (QA). | `Verificar_cobertura` |
| **`TL_Review`** | **Veredito GO/NO-GO**. Cruza código com testes, audita documentação e arquitetura. | Code Review crítico oficial. | `TL_Review no #ServicoCore.ext` |
| **`Valida_ferramentas`** | Simula checagens de pipeline: SonarQube, SAST (segurança) e SCA (pacotes velhos). | Revisão de segurança / DevSecOps. | `Valida_ferramentas neste bloco` |
| **`Explicar_fluxo`** | Rastreia a jornada do dado apontando falhas de tratamento de erro ou telemetria. | Debugging e caça a bugs silenciosos. | `Explicar_fluxo do worker de carga` |
| **`Review_critico`** | Uma revisão focada apenas nas boas práticas e sintaxe da linguagem. | Pair programming / Refinamento local. | `Review_critico` |
| **`Valida_build`** | O "Boss Final". Consolida cobertura, segurança e documentação antes do Merge. | Liberação de Release. | `Valida_build` |

------------

## 💡 5. Como Calibrar este Template para Novos Projetos
1.  **Defina a Stack:** No arquivo de instruções IA, substitua os placeholders `[FRAMEWORK_TESTES]`, `[LINGUAGEM]` e as tecnologias específicas (ex: Node.js, Spring Boot).
2.  **Mapeie Caminhos:** Certifique-se de que os comandos `Bora` apontam para as pastas reais do novo repositório.
3.  **Tolerância Zero:** A IA cobrará qualidade máxima (testes e docs). Não diminua a régua!

------------

#### 📝 Controle de Documentação
- **📅 Última Atualização:** Abril 2026
- **👤 Responsável Técnico:** Willian Marciano
- **✅ Status:** 
