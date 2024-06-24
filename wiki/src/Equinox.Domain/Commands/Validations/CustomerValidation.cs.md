# CustomerValidation.cs: Validação de Cliente

## Visão Geral
Este arquivo define uma classe abstrata `CustomerValidation<T>`, que é usada para validar os comandos do cliente. A classe define regras de validação para o nome, data de nascimento, e-mail e ID do cliente.

## Fluxo do Processo
```mermaid
classDiagram
    CustomerValidation<T> : +void ValidateName()
    CustomerValidation<T> : +void ValidateBirthDate()
    CustomerValidation<T> : +void ValidateEmail()
    CustomerValidation<T> : +void ValidateId()
    CustomerValidation<T> : +bool HaveMinimumAge(DateTime)
    class CustomerValidation<T>{
        -AbstractValidator<T> where T : CustomerCommand
    }
```

## Insights
- A classe `CustomerValidation<T>` é uma classe abstrata e não pode ser instanciada diretamente. Ela deve ser herdada por outras classes que desejam implementar validação de cliente.
- A classe define quatro métodos de validação: `ValidateName()`, `ValidateBirthDate()`, `ValidateEmail()` e `ValidateId()`. Cada método define regras de validação para um atributo específico do cliente.
- O método `HaveMinimumAge(DateTime)` é um método auxiliar usado para verificar se o cliente tem pelo menos 18 anos de idade.

## Dependências (Opcional)
- A classe `CustomerValidation<T>` depende da classe `AbstractValidator<T>` do pacote FluentValidation.
- A classe também depende da classe `CustomerCommand`, que é o tipo genérico `T` usado na classe.

```mermaid
graph LR
    CustomerValidation --|"Depende"| AbstractValidator
    CustomerValidation --|"Depende"| CustomerCommand
```

- `AbstractValidator<T>`: Classe base para todas as classes de validação no FluentValidation. É usada para definir as regras de validação.
- `CustomerCommand`: Classe que representa um comando de cliente. É o tipo genérico `T` usado na classe `CustomerValidation<T>`.

## Vulnerabilidades
- A classe `CustomerValidation<T>` não verifica se a data de nascimento fornecida é uma data futura. Isso pode levar a resultados de validação incorretos.
- A classe não verifica se o e-mail fornecido é único. Isso pode levar a duplicação de clientes.