## Regras Estritas de Nomenclatura e Tradução
Nós nomeamos domínios e lógicas em Português, mas NUNCA traduzimos as APIs e tipos estruturais do framework.
| Nós criamos (PT-BR) | Não traduzir (Framework) |
|---|---|
| `<NomeDoProjeto>Contexto`, `Configuracao<Entidade>` | `DbContext`, `IHostedService` |
| `Worker<Acao>` | `Program.cs`, `CancellationToken` |
| `<Entidade>Controller` | `ControllerBase`, keywords reservadas |

## Estrutura de Testes
Os testes devem espelhar fisicamente a fatia do código que estão cobrindo na pasta do projeto de testes (`tests/<NomeDoProjeto>.Tests/`):
- Camada de Domínio → Pasta correspondente ao Domínio.
- Infraestrutura → Pasta correspondente a Infra (ex: uso de InMemory/Fakes).
- API/Endpoints → Pasta de Contratos/Integração.
**Obrigatório:** Padrão AAA (Arrange, Act, Assert), biblioteca de Mocks estritos apenas para interfaces que tocam I/O, e comentários XML (`///`) de documentação de testes redigidos em Inglês. Código sem teste não pode ser marcado como concluído.