# Desafio-dio-proj-automacao-testes-cypress
DESAFIO DIO Projeto: Automação de Testes com Cypress Objetivo.    
# Desafio Dio -  Projeto: Automação de Testes com Cypress

## Objetivo

Automatizar testes funcionais e de API utilizando **Cypress**. O projeto seguirá um padrão estruturado e incluirá a adição de **identificadores únicos** para facilitar a manutenção e a identificação dos testes.

## Estrutura do Projeto

### 1. Configuração Inicial

- **Instalação do Cypress**

  - Certifique-se de que o **Node.js** está instalado.

  - Crie um novo diretório para o projeto e navegue até ele.

  - Execute o comando:

    bash

    

    ```bash
    npm init -y
    npm install cypress --save-dev
    ```

- **Abertura do Cypress**

  - Após a instalação, abra o

     

    Cypress

     

    com o comando:

    bash

    

    ```bash
    npx cypress open
    ```

### 2. Estrutura de Pastas

- ```
  cypress/
  ```

  - `fixtures/` - Arquivos de dados de teste.
  - `integration/` - Testes funcionais e de API.
  - `plugins/` - Plugins do Cypress.
  - `support/` - Comandos e configurações de suporte.

### 3. Adicionando Identificadores Únicos

- Utilize atributos

   

  ```
  data-*
  ```

   

  para adicionar identificadores únicos aos elementos HTML que serão testados. Por exemplo:

  plaintext

  

  ```plaintext
  <button data-cy="submit-button">Enviar</button>
  ```

## Instruções para Testes Funcionais

### 1. Criando um Teste Funcional

- No diretório `cypress/integration/`, crie um arquivo chamado `funcional.spec.js`.

- Exemplo de teste:

  javascript

  

  ```javascript
  describe('Teste Funcional', () => {
    it('Deve permitir o envio de um formulário', () => {
      cy.visit('URL_DO_SEU_SITE');
      cy.get('[data-cy=submit-button]').click();
      cy.get('[data-cy=success-message]').should('be.visible');
    });
  });
  ```

## Instruções para Testes de API

### 1. Criando um Teste de API

- No diretório `cypress/integration/`, crie um arquivo chamado `api.spec.js`.

- Exemplo de teste:

  javascript

  

  ```javascript
  describe('Teste de API', () => {
    it('Deve retornar um status 200 na API', () => {
      cy.request('GET', 'URL_DA_SUA_API')
        .its('status')
        .should('eq', 200);
    });
  });
  ```

## Padrões e Boas Práticas

- **Nomenclatura**: Use nomes descritivos para os testes e arquivos.
- **Organização**: Mantenha os testes organizados por funcionalidade ou área do sistema.
- **Reutilização**: Crie comandos customizados em `cypress/support/commands.js` para evitar duplicação de código.

## Conclusão

Este projeto de automação de testes com Cypress proporciona uma base sólida para realizar testes funcionais e de API de forma eficiente. A adição de identificadores únicos e a organização da estrutura do projeto garantem que os testes sejam fáceis de manter e compreender.
