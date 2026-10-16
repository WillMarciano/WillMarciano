# COMANDOS_AUXILIARES.md — Caixa de Ferramentas Genérica

Execute a ferramenta solicitada respeitando as tags, pastas (`[BE]` ou `[FE]`) e as tecnologias definidas na Seção 1 do `AI_ROUTER.md`.

## Desenvolvimento Backend
- **`Scaffold_feature`**: Gera a estrutura vertical completa respeitando as camadas definidas no `ARQUITETURA.md` (ex: Domain → Teste Domain → Infra → Teste Infra → API → Teste Endpoint). Aciona gatilho `PADROES.md`.
- **`Gerar_teste`**: Cria testes unitários/integração usando o framework da stack ativa no padrão AAA (Arrange, Act, Assert) e Mocks estritos para I/O. Roda o utilitário de teste localmente. Prioridade: máquina de estados, concorrência e regras críticas. Aciona gatilho `PADROES.md`.
- **`Refactor_this`**: Resolve code smells, reduz complexidade ciclomática e aplica padrões limpos no arquivo atual.
- **`Map_dto`**: Gera o mapeamento explícito Entidade ↔ DTO usando objetos imutáveis (`records` ou equivalentes nativos da linguagem), sem bibliotecas proibidas no `AI_ROUTER.md`.
- **`Espelhar_padrao`**: Copia o estilo arquitetural, nomenclatura e estrutura exata de um arquivo de referência existente no projeto.

## Desenvolvimento Frontend
- **`Explicar_front`**: Antes de gerar o código, fornece de 5 a 10 linhas teóricas explicando a estrutura adotada (componente, estado, propriedades e reatividade no framework ativo) sem jargões.
- **`Tela`**: Constrói uma tela ou componente isolado por vez (ex: listagem, detalhes, modal, login, dashboard), garantindo responsividade.
- **`Ligacao_api`**: Cria exclusivamente a camada de serviço/cliente HTTP tipada consumindo a variável de ambiente de URL da API do projeto.

## Conversão de Stack e Modernização
- **`Converter_sistema`**: Analisa qualquer sistema de origem (legado desktop/web ou outra linguagem moderna), mapeia arquitetura, banco e regras de negócio, e cria o plano completo de migração dividido em fases no `ESCOPO.md`. Se a stack destino não for informada, propõe 3 opções arquiteturais com Mermaid e PARA aguardando aprovação; se a stack destino for informada, adota direto e gera os arquivos da matriz.
- **`Extrair_dominio`**: Faz engenharia reversa de arquivos do sistema de origem (classes, telas, controllers ou scripts SQL), isola regras de negócio, validações e fluxos de estado, e traduz para o `NEGOCIO.md` e entidades limpas na stack alvo.

## Infraestrutura e Operação
- **`AS_IS_System`**: Audita o estado atual dos repositórios físicos contra o checklist do `ESCOPO.md` e a topologia do `ARQUITETURA.md`.
- **`Discovery_completo`**: Mapeia contexto de banco de dados, rotas/endpoints e entidades existentes na fase atual.
- **`Planejar_infra`**: Estrutura o desenho de hospedagem, banco de dados, storage e CI/CD conforme o `ARQUITETURA.md`.
- **`Otimizar_custos`**: Analisa e otimiza o consumo de recursos de nuvem (camadas gratuitas, caching, dimensionamento de containers e prevenção de cold start).
- **`Container_local`**: Executa build e inicialização de containers locais utilizando exclusivamente a ferramenta de container permitida no `AI_ROUTER.md`.

## Qualidade, Segurança e Análise
- **`TL_Review`**: Revisão Tech Lead (GO/NO-GO). Valida testes, compilação, travas de negócio e dispara automaticamente em sequência: `Pre_Sonar`, `Pre_Checkmarx` e `Pre_Mend`.
- **`Review_critico`**: Audita o código para eliminar over-engineering, acoplamentos indevidos e violações do `PADROES.md`.
- **`Tunar_performance`**: Otimiza índices de banco de dados, queries do ORM/SQL e estratégias de cache nos endpoints de maior carga.
- **`Auditar_privacidade`**: Garante que dados sensíveis (LGPD) e campos restritos mapeados no `NEGOCIO.md` nunca vazem em endpoints públicos, payloads ou logs.
- **`Investigar_incidente`**: Analisa stack traces, logs de erro e falhas de concorrência/deadlocks propondo a correção na causa raiz.
- **`Verificar_cobertura`**: Avalia a cobertura de testes focando nas transações críticas e regras do `NEGOCIO.md`, ignorando métricas de vaidade.
- **`Explicar_fluxo`**: Detalha de ponta a ponta o ciclo da máquina de estados e regras críticas definidas no `NEGOCIO.md`.
- **`Validar_concorrencia`**: Verifica se requisições simultâneas no mesmo recurso respeitam as travas de concorrência (ex: Optimistic/Pessimistic Locking retornando conflito HTTP 409).
- **`Revisar_contrato`**: Compara os endpoints e payloads implementados na API contra os requisitos do `ESCOPO.md` e `NEGOCIO.md`.
- **`Gerar_diagrama`**: Produz diagramas Mermaid atualizados da arquitetura ou da máquina de estados do domínio.
- **`Valida_build`**: Executa a compilação final de Backend e Frontend exigindo zero warnings e exit code 0.
- **`Pre_Checkmarx`**: Pré-validação SAST local (regras do Checkmarx). Roda automaticamente no `TL_Review` e `Fechar_Release`. Inspeciona o código-fonte contra SQL Injection, XSS, Path Traversal, Deserialização Insegura, segredos hardcoded e executa os analisadores de segurança estática da stack ativa. Reprova em qualquer falha High/Critical.
- **`Pre_Mend`**: Pré-validação SCA local (regras do Mend). Roda automaticamente ao instalar pacotes novos, no `TL_Review` e no `Fechar_Release`. Audita CVEs em bibliotecas de terceiros usando o gerenciador de pacotes da stack ativa e bloqueia licenças restritivas/contaminantes (ex: GPL/AGPL).
- **`Pre_Sonar`**: Pré-validação de Quality Gate local (regras do SonarQube). Roda automaticamente no `TL_Review` e `Fechar_Release`. Exige compilação e linter com zero warnings, avalia complexidade ciclomática, duplicação de código, code smells e cobertura mínima de testes.