#### Explicação da Estrutura

- **controllers/** → Este diretório armazenará todos os controladores da aplicação que recebe os dados informados pelo usuário e decide o que fazer com eles e cada método deve realizar uma ação ou chamar view. Além disso, toda classe criada herda os métodos da classe Controller do arquivo armazenado em Application/core/Controller.php que será discutido em breve.

- **core/** → Neste diretório será armazenado três arquivos: 
    - **App.php** que é responsavel por tratar a URL decidindo qual controlador e qual método deve ser executado;
    - **Controller.php** responsável por chamar o __model__, __view__ e __pageNotFound__ que são herdados para as classes no diretório Application/controllers
    - E por último, o arquivo **Database.php** que armazena a conexão com o banco de dados.

- **models/** → Aqui fica a lógica das suas entidades, no nosso caso usaremos classes que irá interagir com o banco de dados e fornecer tais dados para as views.

- **views/** → As views serão responsável por interagir com o usuário. Uma das suas principais características é que cada view sabe como exibir um model.

- **.htaccess** → Neste arquivo, apenas negaremos a navegação no diretório com a opção Options -Indexes.

- **autoload.php** → Neste arquivo, carregaremos de forma automática todas as classes no diretório Application/.

#### SQL das tabelas

###### Criação da tabela user:

```SQL
CREATE TABLE `mvc_db`.`users` (
  `idusers` INT NOT NULL AUTO_INCREMENT,
  `name` TEXT(200) NOT NULL,
  PRIMARY KEY (`idusers`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;
```

#### Comandos

- Para rodar, na raiz do projeto digite: **php -S localhost:8080 -t public/**

#### URL de exemplos

- Home: http://localhost:8080/home
- Listar usuários: http://localhost:8080/user
- Buscar um único usuário: http://localhost:8080/user/show/1