# vsCode for Python Developers

Estudo de PI fazendo uso do treinamento Linkedin Learning, vsCode for Python Developers

## Autenticação do repositório Github no vsCode Editor

Uma dificuldade que o estudante pode encontrar é autenticar a contado Github no vsCode, para isso o mesmo pode fazer uso
das dicas encontradas no blog abaixo ou no video de youtube que explica essa questão muito bem.

Eu criei um Token para autenticação do repositório no vsCode localmente na minha máquina, mas outras formas de autenticação
são permitidas.

[Dicas de como autenticar a conta Github](https://www.shellhacks.com/git-config-username-password-store-credentials/)

**Git – Config Username & Password – Store Credentials** Posted on July 19, 2019by admin
Para se conectar a um repositório Git com autenticação via HTTP (S), toda vez que ele precisa definir um nome de usuário e senha.

Você pode configurar o Git para lembrar um nome de usuário e senha armazenando-os em uma URL remota ou usando o ajudante de credencial Git.

Neste artigo, estou mostrando como clonar o repositório Git definindo um nome de usuário e senha na linha de comando, como salvar um nome de usuário e senha no armazenamento de credenciais Git e como configurar diferentes nomes de usuário e senhas para diferentes repositórios no mesmo servidor Git.

![image](https://user-images.githubusercontent.com/33582443/133961361-b7b6efd0-5f37-43c0-839d-4f9d81efa972.png)

## Definir nome de usuário e senha no URL remoto

Para salvar as credenciais, você pode clonar o repositório Git definindo um nome de usuário e uma senha na linha de comando:

![image](https://user-images.githubusercontent.com/33582443/133961582-64eebdc6-b956-4db8-bfb5-7249a6e4e2cc.png)

O nome de usuário e a senha serão armazenados no .git/configarquivo como parte da URL do repositório remoto.

Se você já clonou um repositório sem definir o nome de usuário e a senha na linha de comando, pode sempre atualizar o URL remoto executando o seguinte comando:

![image](https://user-images.githubusercontent.com/33582443/133962073-1a3255f4-a64f-4344-b3ec-1484ce688ccb.png)

## Salvar nome de usuário e senha no armazenamento de credenciais Git

Execute o seguinte comando para habilitar o armazenamento de credenciais em seu repositório Git:

![image](https://user-images.githubusercontent.com/33582443/133962261-65757271-d7f6-496e-88a2-735f53d756a7.png)

Para habilitar o armazenamento de credenciais globalmente, execute:

![image](https://user-images.githubusercontent.com/33582443/133962323-9be753bc-57e7-45cf-8d2f-4972d75f2a20.png)

Quando o armazenamento de credenciais está habilitado, na primeira vez que você puxa ou faz push do repositório Git remoto, será solicitado um nome de usuário e uma senha, e eles serão salvos em um ~/.git-credentialsarquivo.

Durante as próximas comunicações com o repositório Git remoto, você não precisará fornecer o nome de usuário e a senha.

Cada credencial no ~/.git-credentialsarquivo é armazenada em sua própria linha como um URL como:

![image](https://user-images.githubusercontent.com/33582443/133962461-9b07c848-be4e-43da-83bc-819fc883abe2.png)

## Config nome de usuário e senha para diferentes repositórios

Às vezes, você pode precisar usar contas diferentes no mesmo servidor Git, por exemplo, a conta corporativa da sua empresa em github.com e a conta privada.
Para poder configurar nomes de usuário e senhas para diferentes repositórios Git no mesmo servidor Git, você pode habilitar a opção useHttpPath.

>Por padrão, o Git não considera o componente “caminho” de uma URL http para ser correspondido por meio de ajudantes externos. Isso significa que uma credencial armazenada para >https://example.com/foo.git também será usada para https://example.com/bar.git. Se você quiser distinguir esses casos, defina a opção useHttpPath como verdadeiro ( fonte )

Execute os seguintes comandos para configurar o armazenamento de credenciais Git e separar credenciais para diferentes repositórios em github.com :

![image](https://user-images.githubusercontent.com/33582443/133962752-2d247318-22bc-44fd-b85b-bfbbefb5ad3a.png)

The usernames and passwords for different GitHub repositories will be stored in ~/.git-credentials file separately on their own lines:

https://<USERNAME>:<PASSWORD>@github.com/path/to/repo1.git
https://<USERNAME>:<PASSWORD>@github.com/path/to/repo2.git
