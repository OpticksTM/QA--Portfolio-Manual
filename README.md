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

---

# 3. Fluxo de Carrinho e Checkout
Sistema testado: SauceDemo (https://www.saucedemo.com/)

Funcionalidade: Adicionar produtos, gerenciar o carrinho e preencher dados de entrega

| ID | Cenário de Teste | Comportamento Esperado | Status |
| --- | --- | --- | --- |
| CT06 | Adicionar um produto ao carrinho na vitrine. | O ícone do carrinho deve atualizar o contador exibindo o número "1". | Passou |
| CT07 | Tentar avançar no preenchimento do Checkout sem preencher o campo "First Name". | O sistema deve bloquear o avanço e exibir uma mensagem de erro informando que o campo é obrigatório. | Passou |

---

# 4. Navegação do Menu Lateral e Logout

Sistema testado: SauceDemo (https://www.saucedemo.com/)

Funcionalidade: Menu lateral, navegação e encerramento de sessão

| ID | Cenário de Teste | Comportamento Esperado | Status |
| --- | --- | --- | --- |
| CT08 | Clicar no menu lateral (hambúrguer) e selecionar a opção "Logout". | O sistema deve encerrar a sessão atual e redirecionar o usuário de volta para a tela inicial de login. | Passou |
| CT09 | Tentar retornar à página de produtos utilizando o botão "Voltar" do navegador após realizar o Logout. | O sistema deve barrar o acesso e manter o usuário na tela de login por questões de segurança. | Falhou |

---

## 5. Relatório de Bugs (Bug Report)

* ID do Bug: BUG-01
* Título: Possibilidade de navegar para páginas internas após o Logout usando o botão "Voltar" do navegador.
* Módulo / Tela: Tela de Login e Sessão do Usuário
* Severidade: Alta (Problema de Segurança / Controle de Sessão)
* Ambiente: SauceDemo (https://www.saucedemo.com/) - Navegador Google Chrome

# Descrição:
Após o usuário realizar o processo de Logout com sucesso, o sistema redireciona corretamente para a tela de login. No entanto, ao utilizar o botão "Voltar" (seta para esquerda) do navegador, o sistema permite que o usuário visualize novamente as páginas internas (como o carrinho e o catálogo de produtos) sem estar autenticado.

# Passos para Reproduzir:
1. Acesse o site do SauceDemo e faça login com credenciais válidas (`standard_user` / `secret_sauce`).
2. Abra o menu lateral esquerdo e clique em Logout.
3. Observe que a tela de login é exibida corretamente.
4. Clique no botão "Voltar" (seta para a esquerda) do navegador.

# Resultado Obtido:
O navegador retorna para as telas internas (carrinho/produtos) sem exigir uma nova autenticação.

# Resultado Esperado:
Após o logout, a sessão deve ser completamente destruída. O uso do botão "Voltar" do navegador deve manter o usuário na tela de login ou forçar uma nova autenticação, impedindo o acesso a páginas restritas.

---

# 6. Fluxo de Compra Final (End-to-End)
Sistema testado: SauceDemo (https://www.saucedemo.com/)

Funcionalidade: Preenchimento de dados de entrega, resumo do pedido e finalização da compra

| ID | Cenário de Teste | Comportamento Esperado | Status |
| --- | --- | --- | --- |
| CT10 | Preencher os campos obrigatórios de checkout (First Name, Last Name, Postal Code) e avançar. | O sistema deve direcionar o usuário para a página de resumo do pedido (Checkout Overview) exibindo o produto e os valores corretos. | Passou |
| CT11 | Clicar no botão "Finish" na tela de resumo do pedido. | O sistema deve processar a compra, exibir a tela de sucesso (`Checkout: Complete!`) e a mensagem de agradecimento pelo pedido. | Passou |

