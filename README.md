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

# 2. Relatórios de Bugs (Bug Reports)
Exemplo prático de reporte de falha encontrado durante a exploração do sistema.

Bug 01: Erro de ordenação de valores

Módulo: Página de Produtos (Inventário)

Severidade: Média

Passos para reproduzir:

1. Acessar o site `https://www.saucedemo.com/`

2. Fazer login com o usuário padrão.

3. No filtro de ordenação (canto superior direito), selecionar **"Price (high to low)"** (Preço do maior para o menor).

Resultado Obtido: O sistema mistura alguns valores sem respeitar a ordem decrescente exata no topo da lista.

Resultado Esperado: O produto de maior valor do e-commerce deveria aparecer em primeiro lugar absoluto.
