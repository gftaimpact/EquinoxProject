# ApiController.cs: Controlador API Base

## Visão Geral
O arquivo `ApiController.cs` define uma classe abstrata `ApiController` que estende `ControllerBase`. Esta classe serve como um controlador base para outras classes de controlador na aplicação. Ela fornece métodos para manipular respostas personalizadas e gerenciar erros.

## Fluxo do Processo

```mermaid
graph TD
    A["CustomResponse(object result)"] -->|Verifica se a operação é válida| B{"IsOperationValid()"}
    B --|Se verdadeiro| C["Retorna Ok(result)"]
    B --|Se falso| D["Retorna BadRequest"]
    E["CustomResponse(ModelStateDictionary modelState)"] -->|Adiciona erros do ModelState à lista de erros| F["AddError(error.ErrorMessage)"]
    G["CustomResponse(ValidationResult validationResult)"] -->|Adiciona erros do ValidationResult à lista de erros| F
    H["AddError(string erro)"] -->|Adiciona um erro à lista de erros| I["_errors.Add(erro)"]
    J["ClearErrors()"] -->|Limpa a lista de erros| K["_errors.Clear()"]
```

## Insights
- A classe `ApiController` é abstrata, o que significa que ela não pode ser instanciada diretamente. Ela serve como uma classe base para outros controladores.
- A classe `ApiController` mantém uma coleção privada de erros (`_errors`) que é usada para armazenar mensagens de erro.
- A classe `ApiController` fornece vários métodos `CustomResponse` que permitem criar respostas personalizadas com base em diferentes tipos de entrada.
- O método `IsOperationValid` verifica se há erros na coleção `_errors`.
- Os métodos `AddError` e `ClearErrors` são usados para manipular a coleção de erros.

## Dependências (Opcional)
Não foram identificadas dependências externas neste código.

## Manipulação de Dados (SQL) (Opcional)
Não há manipulação de dados SQL neste código.