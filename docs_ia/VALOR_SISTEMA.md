# Controle Comercial e Valor do Sistema

**Última atualização:** YYYY-MM-DD
**Produto:** [Nome Genérico do Sistema]

> **Regra para a IA:** O comando diário `Bora` DEVE IGNORAR este ficheiro. A leitura ou alteração deste documento só é permitida sob invocação explícita do comando `Atualizar_valor`, que OBRIGA a leitura prévia do `CHANGELOG.md` para mapear as entregas técnicas recentes. NUNCA invente preços ou regras comerciais sem a aprovação do utilizador.

Este documento controla o valor comercial do software entregue, separando o custo do código das despesas de infraestrutura.

---

## 1. O Produto Hoje

| Critério | Status Atual |
|---|---|
| **Degrau de Maturidade** | **A** (MVP Funcional no Ar) |
| **Modelo de Venda** | Instalação única por cliente (On-premise / Nuvem dedicada) |
| **Expansibilidade** | Pronto para escalar para SaaS (requer multi-tenant no futuro) |

---

## 2. Degraus de Mercado e Precificação (Referência)

Esta tabela define quanto o sistema vale no mercado conforme ganha novas funcionalidades. *Os valores são referenciais e devem ser ajustados pela equipa humana.*

| Degrau | Entregáveis Principais | Faixa de Preço (Setup) | Mensalidade / Suporte |
|---|---|---|---|
| **A - MVP** | Funcionalidades base, fluxos essenciais, 1 utilizador admin. | R$ X.XXX a R$ Y.YYY | R$ XXX / mês |
| **B - Intermediário** | Pagamentos automatizados, dashboards avançados, relatórios. | R$ X.XXX a R$ Y.YYY | R$ XXX / mês |
| **C - SaaS Pleno** | Multi-tenant, onboarding automático, personalização avançada. | (Setup Baixo) | R$ XXX a R$ YYY / mês |

---

## 3. Pacote Comercial Atual (Degrau A)

O que está incluído na venda atual do sistema:

### O que o cliente PAGA no pacote:
- Cópia e deploy dos repositórios (Frontend e Backend).
- Configuração inicial de ambiente e base de dados limpa.
- Treinamento básico de uso.
- **Garantia de XX dias:** Correção de bugs introduzidos pela nossa equipa.

### O que o cliente NÃO PAGA no pacote (Custos Extra):
- **Alojamento / Nuvem:** Custos mensais de AWS/Render/Vercel ficam no cartão do cliente.
- **Novas Features:** Qualquer funcionalidade fora do escopo original exige novo orçamento.
- **Suporte Pós-Garantia:** Cobrado via pacote de horas ou mensalidade de manutenção.

---

## 4. Histórico de Valorização

*Atualizado exclusivamente pelo comando `Atualizar_valor` após cruzamento com o `CHANGELOG.md`.*

| Data | Marco Entregue (Feature/Fase) | Degrau | Novo Valor Base (Setup) |
|---|---|---|---|
| YYYY-MM-DD | Setup inicial do MVP e arquitetura base. | A | R$ X.XXX,00 |