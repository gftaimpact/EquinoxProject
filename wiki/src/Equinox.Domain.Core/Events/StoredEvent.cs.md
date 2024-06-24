# StoredEvent.cs: Armazenamento de Eventos

## Visão Geral
O arquivo `StoredEvent.cs` define uma estrutura de dados chamada `StoredEvent` que herda da classe `Event`. Esta estrutura é usada para armazenar eventos com informações como `Id`, `Data` e `User`.

## Fluxo do Processo
Como `StoredEvent` é uma estrutura de dados, um diagrama de classe ou uma tabela com os atributos relacionados seria mais apropriado para representar suas características.

| Atributo | Tipo | Descrição |
|----------|------|-----------|
| Id | Guid | Identificador único do evento. |
| Data | string | Dados associados ao evento. |
| User | string | Usuário associado ao evento. |

## Insights
- A estrutura de dados `StoredEvent` é usada para armazenar eventos com informações como `Id`, `Data` e `User`.
- `StoredEvent` herda da classe `Event`, o que significa que ela também possui os atributos `AggregateId` e `MessageType` da classe `Event`.
- O construtor de `StoredEvent` aceita um evento, dados e usuário como parâmetros e inicializa o `Id` com um novo `Guid`.
- Existe um construtor protegido sem parâmetros para `StoredEvent`, que é necessário para o Entity Framework.

## Dependências (Opcional)
Não foram identificadas dependências externas neste código.

## Vulnerabilidades
Não foram identificadas vulnerabilidades neste código.