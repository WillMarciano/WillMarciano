# Regras de Negócio e Domínio

**Domínio Atual:** [Nome do Projeto / Empresa]

> **Regra Mestra para a IA:** Este arquivo dita a LÓGICA DE NEGÓCIO. Se a regra descrita aqui conflitar com qualquer padrão técnico genérico ou suposição sua, A REGRA DESTE ARQUIVO PREVALECE. Nunca invente regras de negócio, cálculos ou restrições de acesso que não estejam listados abaixo.

## 1. Glossário e Ubiquitous Language
*Definição dos termos exatos que devem ser usados no código e no banco de dados para evitar ambiguidades.*
- **`[Entidade_Principal]`**: O que é, o papel dela no sistema e seu identificador único.
- **`[Entidade_Secundaria]`**: Como se relaciona com a principal (ex: 1 para N, N para N).

## 2. Máquina de Estados (Ciclo de Vida)
*Como os status das entidades principais evoluem e quais os gatilhos para essa mudança.*
- **Status `[Inicial]`**: Estado ao ser criado.
- **Transição `[Acao_1]`**: Muda o status de `[Inicial]` para `[Intermediario]`. Regra: Só pode ocorrer se a condição X for atendida.
- **Transição `[Acao_2]`**: Muda o status para `[Final/Cancelado]`.

## 3. Transações Críticas e Concorrência
*Regras sobre o que acontece quando múltiplos usuários tentam agir sobre o mesmo recurso.*
- **Regra de Bloqueio:** O que acontece se duas requisições tentarem modificar o recurso `[X]` ao mesmo tempo? (ex: `SELECT FOR UPDATE`, Optimistic Concurrency).
- **Consistência:** A entidade `[X]` só pode ser excluída/inativada se não houver vínculos ativos com `[Y]`.

## 4. Segurança, LGPD e Anti-Abuso (Rate Limit)
*Definições de privacidade de dados, papéis de acesso e limites de requisição.*
- **Dados Sensíveis (LGPD):** Os campos `[Campo_A]` e `[Campo_B]` NUNCA devem ser expostos em endpoints públicos (GET sem autenticação). Eles devem trafegar mascarados ou cifrados.
- **Autenticação e Permissões:** 
  - Ações de leitura pública: [Definir escopo].
  - Ações de mutação (POST/PUT/DELETE): Exigem autenticação via JWT com a role `[Role_Autorizada]`. É proibido criar rotas de bypass baseadas em tokens na URL.
- **Rate Limit e Throttling:**
  - `POST /api/auth/...`: Estoura HTTP 429 após `[X]` falhas em `[Y]` minutos (Base de cálculo: IP + Identificador).
  - `POST /api/[recurso_critico]`: Estoura HTTP 429 após `[W]` tentativas para evitar ataques de exaustão ou spam.