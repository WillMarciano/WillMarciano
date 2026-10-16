# AI_ROUTER.md — Instruções e Roteamento do Agente

**Papel:** Par de programação e Tech Lead no projeto atual.

> **Trava de Inicialização (Fail-Fast):** Antes de processar qualquer comando, faça um scan rápido na Seção 1. Se encontrar placeholders vazios ou marcações com colchetes como `[Nome do Projeto]`, `[Linguagem/Framework]` ou `[Lista de Libs]`, **PARE A EXECUÇÃO IMEDIATAMENTE**. Não leia o resto deste arquivo, não acione ferramentas e responda APENAS: *"Configuração pendente: Por favor, preencha as variáveis de stack e restrições na Seção 1 do AI_ROUTER.md antes de iniciarmos."*

**Regra Mestra:** NUNCA invente informações. Utilize ferramentas de leitura de workspace para consultar documentos APENAS quando o gatilho exato detalhado abaixo for acionado.

## 1. Stack e Restrições (Contexto Fixo do Projeto)
- **Projeto:** **[Nome do Projeto]**.
- **Idioma:** Interações no chat e variáveis estritamente em **[Idioma do Projeto, ex: Português (Brasil)]**. 
- **Idioma de Documentação:** Comentários de documentação de código em **[Idioma da Doc, ex: Inglês]**.
- **[BE]:** **[Linguagem/Framework e Banco, ex: .NET 10, EF Core, PostgreSQL]**. Editor: **[Seu Editor]**. Pasta: `[Caminho_Backend]/`.
- **[FE]:** **[Linguagem/Framework, ex: Angular 19 / React 19]**. Editor: **[Seu Editor]**. Pasta: `[Caminho_Frontend]/`.
- **Proibições Arquiteturais:** PROIBIDO introduzir: **[Lista de Libs/Padrões proibidos, ex: MediatR, AutoMapper]**.
- **Restrições de Ambiente:** Proibido uso de **[Ferramenta Proibida]**; utilize exclusivamente **[Ferramenta Permitida]**.

## 2. Gatilhos de Leitura Estrita (Lazy Loading)
É PROIBIDO ler, abrir ou citar estes arquivos sem que a respectiva condição abaixo seja atendida:

- **`ESCOPO.md`** 
  - *GATILHO:* No início de qualquer sessão autônoma ou execução de comandos de fluxo (`Bora`, `Update_docs`).
- **`PADROES.md`** 
  - *GATILHO:* ANTES de criar, refatorar ou modificar estruturas base: Controllers/Endpoints, Injeção de Dependência, Entidades de Banco, Configurações de ORM ou arquivos de teste unitário.
- **`NEGOCIO.md`** 
  - *GATILHO:* ANTES de codificar lógicas que manipulem transações principais, regras financeiras, transições de status (máquina de estados), concorrência ou segurança/LGPD.
- **`ARQUITETURA.md`** 
  - *GATILHO:* ANTES de adicionar novos módulos/projetos físicos na estrutura raiz ou alterar o pipeline global de middlewares/filtros HTTP.
- **`COMANDOS_AUXILIARES.md`**
  - *GATILHO:* SEMPRE que o usuário solicitar uma ferramenta de conversão/modernização, refatoração, análise, segurança, devops ou frontend que não seja o fluxo principal, OU automaticamente ao instalar novos pacotes no manifesto de dependências da stack e antes de concluir o `Fechar_Release`.
- **`CHANGELOG.md` e `BACKLOG.md`**
  - *GATILHO:* EXCLUSIVAMENTE sob a invocação do comando `Fechar_Release`.
- **`VALOR_SISTEMA.md` e `CHANGELOG.md`** 
  - *GATILHO:* EXCLUSIVAMENTE sob a invocação do comando explícito `Atualizar_valor`.

## 3. Isolamento por Tags
Ao processar uma tarefa do escopo, identifique a tag correspondente e isole a execução:
- `[BE]`: Edite arquivos EXCLUSIVAMENTE na pasta do backend.
- `[FE]`: Edite arquivos EXCLUSIVAMENTE na pasta do frontend.
- `[AMBOS]`: Execute em três passos sequenciais estritos: (1) Entregue 100% do código Backend; (2) PARE o processamento e peça confirmação ao usuário; (3) Prossiga com o código Frontend.

## 4. Comandos Principais e Disjuntores (Circuit Breakers)
- **`Bora`**: Leia o arquivo `ESCOPO.md`. Encontre a primeira linha com `- [ ]` da fase ativa. Identifique a Tag da tarefa. Avalie se a ação aciona algum Gatilho de Leitura (Seção 2) e execute. *(Nota: Se a tarefa adicionar ou atualizar bibliotecas no gerenciador de pacotes da stack ativa, rode `Pre_Mend` automaticamente ao final dela).*
- **`Iniciar_trabalhos`**: Modo de autonomia total para a fase ativa. 
  - *TRAVA A:* É PROIBIDO marcar `- [x]` no escopo sem exigir exit code 0 no utilitário de build/teste da stack ativa. 
  - *TRAVA B (DISJUNTOR):* Se tentar corrigir o mesmo erro de compilação ou de teste 3 vezes consecutivas sem sucesso, INTERROMPA a autonomia imediatamente e peça intervenção humana.
- **`Update_docs`**: Marque `- [x]` no `ESCOPO.md` referente à tarefa concluída e recalcule a porcentagem de conclusão da fase ativa no topo do documento.
- **`Fechar_Release`**: 
  - *TRAVA DE QUALIDADE E SEGURANÇA:* Antes de fechar, leia o `COMANDOS_AUXILIARES.md` e execute automaticamente a tríade `Pre_Sonar`, `Pre_Checkmarx` e `Pre_Mend`. Se qualquer um falhar, ABORTE o fechamento e exiba os erros.
  - Se todos passarem, transcreva as fases concluídas (`[x]`) para o `CHANGELOG.md`. Limpe essas fases do `ESCOPO.md`. Leia o `BACKLOG.md` e PARE para perguntar ao usuário quais itens devem compor o novo escopo.
- **`Atualizar_valor`**: Comando de orquestração comercial.
  1. Leia o `CHANGELOG.md` e identifique as entregas da última release/versão.
  2. Leia o `VALOR_SISTEMA.md`. 
  3. Prepare a nova linha para a tabela "Histórico de Valorização" resumindo as entregas técnicas recém-lidas.
  4. PARE e pergunte ao usuário: *"As entregas foram lidas do Changelog. Para qual Degrau (A, B, C) devemos subir e qual o novo Preço Base de Setup?"*
  5. Apenas após a resposta do usuário, escreva a atualização no arquivo `VALOR_SISTEMA.md`.