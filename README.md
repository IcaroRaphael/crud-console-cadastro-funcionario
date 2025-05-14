# Sistema de Cadastro de Funcionários em Console (C#)

Este é um simples aplicativo de console em C# para gerenciar informações de funcionários. Ele permite cadastrar, visualizar, atualizar e deletar registros de funcionários.

## Funcionalidades

*   **Cadastrar Funcionário:** Adiciona um novo funcionário com nome, cargo e salário.
*   **Visualizar Funcionários:** Lista todos os funcionários cadastrados com seus respectivos IDs, nomes, cargos e salários.
*   **Atualizar Funcionário:** Permite modificar o nome, cargo ou salário de um funcionário existente, selecionado por ID.
*   **Deletar Funcionário:** Remove um funcionário do sistema, selecionado por ID.
*   **Sair do Programa:** Encerra a aplicação.

## Estrutura do Código

O código está organizado da seguinte forma:

*   **`Program.cs`**: Contém a lógica principal da aplicação.
    *   **`Main`**: Ponto de entrada do programa, contém o loop principal que exibe o menu e direciona para as funcionalidades escolhidas.
    *   **`funcionarios` (List<Dictionary<string, string>>)**: Estrutura de dados principal para armazenar as informações dos funcionários. Cada funcionário é um dicionário com as chaves "NOME", "CARGO" e "SALARIO".
    *   **Funções de CRUD:**
        *   `CadastrarFuncionario()`: Lida com a entrada de dados e adição de um novo funcionário.
        *   `VisualizarFuncionarios()`: Exibe a lista de funcionários cadastrados.
        *   `AtualizarFuncionario()`: Permite ao usuário selecionar um funcionário por ID e atualizar um de seus campos (nome, cargo ou salário).
        *   `DeletarFuncionario()`: Permite ao usuário selecionar um funcionário por ID e removê-lo da lista.
    *   **Funções de Menu:**
        *   `Menu()`: Exibe o menu principal e captura a escolha do usuário.
        *   `MenuAtualizar()`: Exibe o submenu para escolher qual campo do funcionário atualizar.
    *   **Funções de Validação:**
        *   `ValidarId()`: Garante que o ID inserido pelo usuário seja um número válido e dentro do intervalo de funcionários existentes.
        *   `ValidarSalario()`: Garante que o salário inserido seja um número e o formata como moeda.
        *   `ValidarNome()`: Garante que o nome inserido não contenha números e tenha pelo menos 3 letras.
        *   `ValidarCargo()`: Garante que o cargo inserido não contenha números e tenha pelo menos 3 letras.
    *   **Função de Confirmação:**
        *   `ConfirmaEscolha()`: Pede ao usuário uma confirmação ("SIM") antes de realizar ações como cadastro, atualização ou deleção.

## Como Executar

1.  **Pré-requisitos:**
    *   [.NET SDK](https://dotnet.microsoft.com/download) instalado.

2.  **Compilar e Executar:**
    *   Salve o código em um arquivo chamado `Program.cs`.
    *   Abra um terminal ou prompt de comando na pasta onde você salvou o arquivo.
    *   Compile o projeto (se necessário, crie um projeto console primeiro com `dotnet new console`):
        ```bash
        dotnet build
        ```
    *   Execute o aplicativo:
        ```bash
        dotnet run
        ```

## Validações Implementadas

O sistema inclui as seguintes validações de entrada para garantir a integridade dos dados:

*   **Nome e Cargo:**
    *   Não podem conter números.
    *   Devem possuir ao menos 3 letras (desconsiderando espaços).
*   **Salário:**
    *   Deve ser um valor numérico (double).
    *   É formatado como moeda (ex: R$ 1.234,56) ao ser armazenado.
*   **ID do Funcionário:**
    *   Deve ser um número inteiro.
    *   Deve corresponder a um ID existente na lista de funcionários.
*   **Escolhas de Menu:**
    *   Devem ser números inteiros correspondentes às opções disponíveis.
