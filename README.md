Quality Assurance (QA Manual)

Documentação de cenários de teste, planejamento de qualidade e reporte de falhas em aplicações web.

# 1. Planejamento de Testes (Cenários)
Sistema testado: SauceDemo (https://www.saucedemo.com/)

Funcionalidade: Tela de Login

| ID | Cenário de Teste | Comportamento Esperado | Status |
| --- | --- | --- | --- |
| CT01 | Inserir usuário `standard_user` e senha correta `secret_sauce`. | O sistema deve logar com sucesso e redirecionar para a página de produtos. | Passou |
| CT02 | Deixar os campos de usuário e senha em branco e clicar em "Login". | O sistema deve exibir a mensagem de erro: `Epic sadface: Username is required`. | Passou |
| CT03 | Inserir o usuário bloqueado `locked_out_user` e senha correta. | O sistema deve barrar o acesso e exibir a mensagem de usuário bloqueado. | Passou |

---

# 2. Validação de Filtros (Ordenação de Produtos)

Sistema testado: SauceDemo (https://www.saucedemo.com/)

Funcionalidade: Filtro de listagem de produtos

| ID | Cenário de Teste | Comportamento Esperado | Status |
| --- | --- | --- | --- |
| CT04 | Selecionar o filtro "Name (Z to A)" na vitrine de produtos. | Os produtos devem reorganizar a ordem alfabética de forma decrescente, exibindo itens iniciados pelas últimas letras do alfabeto no topo. | Passou |
| CT05 | Selecionar o filtro "Price (low to high)" na vitrine de produtos. | Os produtos devem se organizar do mais barato para o mais caro de forma crescente. | Passou |
