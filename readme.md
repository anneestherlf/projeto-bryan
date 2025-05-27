## 🧠 Perguntas para medir aprendizado (responder neste README)

1. **Explique com suas palavras o papel de cada camada da arquitetura MVC usada neste projeto.**  
   *Como o Model, o Controller e a View interagem entre si?*

O Model é a parte que cuida dos dados. Ele conversa com o banco de dados, saçva, busca, edita e apaga informações. A View é a parte visual, ou seja, o que aparece na tela do usuário (e as páginas HTML). O controller é o "meio". Ele recebe os pedidos do usuário e pede para o Mode mexer nos dados, depois mostra a resposta usando a View.

Eles interagem dessa forma: o Controller recebe o pedido, fala com o Model para salvar o professor no banoc, e depois mostra uma página (View) com o resultado.

2. **Como ocorre o envio e o recebimento de dados no formato JSON neste projeto?**  
   *Cite uma rota que responde em JSON e explique seu funcionamento.*

O envio e o recebimento de dados em JSON acontece quando o servidos responde informações em formato de texto estruturado (JSON), em vez de mostrar uma página HTML. Exemplo de rota:

```javascript 
app.get('/api/professores', async (req, res) => {
    const professores = await Professor.findAll();
    res.json(professores);
});
```
Funcionamento: quando acessamos `/api/professores`, o servidor pega todos os professores do banco de dados e devolve a lista em formato JSON. 

3. **Qual a importância de usar HTML básico com formulários e tabelas para organizar e manipular dados no navegador?**  
   *Por que esse tipo de estrutura ainda é útil em projetos back-end com Node.js?*

Pois o HTML básico com formulários e tabelas é fácil de entender e usar. Ele permite que qualquer pessoa cadastre, edite e veja dados direto pelo navegador, sem precisar de programas especiais. 
Ainda é útil porque facilita testes, aprendizado e uso do sistema por pessoas que não são desenvolvedoras. Além disso, funciona em qualquer navegador e é ótimo para sistemas simples de cadastro e consulta de dados.

---

## 📝 Questão solicitada pelo professor Cristiano: Explique com suas palavras o funcionamento do models, controller e fale sobre endpoints no projeto.

Resposta: <br>
Models são as tabelas de dados do projeto. São os arquivos JavaScript responsáveis por representar e manipular os dados das entidades principais: nesse caso, alunos, cursos e professores.

Controller é responsável por transportar os dados para a parte visual do projeto. Nesse repositório, o controller é responsável por receber as requisições do usuário (quando você clica em "Adicionar", "Editar" ou "Deletar" professor), chamar os métodos do model (como o professor.js) e decidir qual página (view) mostrar como resposta.

Os endpoints são os "endereços" (caminhos/URLs) que o navegador usa para se comunicar com o servidor. Eles dizem para onde os dados do formulário devem ser enviados quando você clica em "Adicionar", "Editar" ou "Deletar".

No projeto, eu utilizei endpoints nos atributos action dos formulários (arquivos index.ejs) para adicionar, editar e deletar professores, alunos e cursos. Esses caminhos são usados pelo navegador para enviar os dados para o servidor.

---------------

# Sobre o projeto:

## Requisitos

- Node.js (versão X.X.X)
- PostgreSQL (versão X.X.X)

## Instalação

1. **Clonar o repositório:**

```bash
   git clone https://github.com/seu-usuario/seu-projeto.git
   cd seu-projeto
```

2. **Instalar as dependências:**
    
```bash
npm install
```
    
3. **Configurar o arquivo `.env`:**

Renomeie o arquivo `.env.example` para `.env` e configure as variáveis de ambiente necessárias, como as configurações do banco de dados PostgreSQL.
    

Configuração do Banco de Dados
------------------------------

1. **Criar banco de dados:**
    
    Crie um banco de dados PostgreSQL com o nome especificado no seu arquivo `.env`.
    
2. **Executar o script SQL de inicialização:**
    
```bash
npm run init-db
```
    
Isso criará as tabelas `users`, `aluno`, `curso` e `professor` no seu banco de dados PostgreSQL com UUID como chave primária e inserirá alguns registros de exemplo.
    

Funcionalidades
---------------

* **Padrão MVC:** Estrutura organizada em Model, View e Controller.
* **PostgreSQL:** Banco de dados relacional utilizado para persistência dos dados.
* **UUID:** Utilização de UUID como chave primária na tabela `users`.
* **Scripts com `nodemon`:** Utilização do `nodemon` para reiniciar automaticamente o servidor após alterações no código.
* **Testes:** Inclui estrutura básica para testes automatizados.

Scripts Disponíveis
-------------------

* `npm start`: Inicia o servidor Node.js.
* `npm run dev`: Inicia o servidor com `nodemon`, reiniciando automaticamente após alterações no código.
* `npm run test`: Executa os testes automatizados.
* `npm run test:coverage`: Executa os testes e gera um relatório de cobertura de código.

Estrutura de Diretórios
-----------------------

* **`config/`**: Configurações do banco de dados e outras configurações do projeto.
* **`controllers/`**: Controladores da aplicação (lógica de negócio).
* **`models/`**: Modelos da aplicação (definições de dados e interações com o banco de dados).
* **`routes/`**: Rotas da aplicação.
* **`tests/`**: Testes automatizados.
* **`views/`**: Views da aplicação (se aplicável).

Licença
-------

Este projeto está licenciado sob a Licença MIT.
