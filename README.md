O MauiAppMinhasCompras é uma aplicação desenvolvida em .NET MAUI com o objetivo de auxiliar o usuário no gerenciamento de listas de compras. O sistema permite cadastrar, editar, pesquisar e remover produtos, além de calcular automaticamente o valor total dos itens registrados.

Os dados são armazenados localmente por meio de um banco de dados SQLite, possibilitando a persistência das informações mesmo após o encerramento da aplicação.

# Funcionamento

A aplicação é composta por duas telas principais: Lista de Produtos e Cadastro de Produto.

# Lista de Produtos

A tela inicial exibe todos os produtos cadastrados, recuperando as informações armazenadas no banco de dados SQLite. Os registros são apresentados em uma lista dinâmica vinculada a uma ObservableCollection, permitindo que as alterações sejam refletidas automaticamente na interface.

Além da visualização dos itens, a tela oferece os seguintes recursos:

Pesquisa de produtos em tempo real através de um campo de busca;
Exclusão de produtos utilizando gesto de deslizar (Swipe), com confirmação da ação por meio de uma caixa de diálogo;
Seleção de itens para edição de suas informações;
Cálculo do valor total da lista por meio da opção "Somar", que percorre todos os produtos cadastrados e apresenta o resultado acumulado ao usuário.
Cadastro de Produto

A segunda tela é responsável pelo cadastro e edição dos produtos. O formulário contém campos para descrição, quantidade e preço unitário.

O comportamento da tela é definido pelo objeto associado ao BindingContext:

Quando não existe um produto vinculado, a aplicação realiza a inserção de um novo registro;
Quando um produto existente é informado, a aplicação executa a atualização dos dados já armazenados.

Após a conclusão da operação, os dados são salvos no banco SQLite e o usuário é redirecionado automaticamente para a tela anterior.

# Conceitos Aplicados

Durante o desenvolvimento deste projeto foram utilizados os seguintes conceitos:

Criação de aplicações multiplataforma utilizando .NET MAUI;
Persistência de dados por meio do banco de dados SQLite;
Operações de inserção, consulta, atualização e exclusão de registros (CRUD);
Utilização de ObservableCollection para atualização dinâmica da interface;
Implementação de navegação entre páginas utilizando Navigation.PushAsync() e Navigation.PopAsync();
Uso de BindingContext para compartilhamento de dados entre interface e lógica da aplicação;
Manipulação de eventos de interface, como seleção de itens e alterações em campos de texto;
Implementação de filtros de pesquisa em tempo real;
Exibição de mensagens de confirmação utilizando métodos nativos da plataforma.




Durante o desenvolvimento também foi utilizada uma estrutura auxiliar para organização do projeto, incluindo a criação da pasta Helpers, responsável por concentrar classes de apoio relacionadas ao acesso e gerenciamento dos dados. Além disso, foi empregada a biblioteca sqlite-net-pcl, que simplifica a comunicação entre a aplicação em C# e o banco de dados SQLite disponível no sistema operacional hospedeiro.
