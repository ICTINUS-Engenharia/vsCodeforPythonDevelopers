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

$ git config credential.helper store
To enable credentials storage globally, run:

$ git config --global credential.helper store
When credentials storage is enabled, the first time you pull or push from the remote Git repository, you will be asked for a username and password, and they will be saved in ~/.git-credentials file.

During the next communications with the remote Git repository you won’t have to provide the username and password.

Each credential in ~/.git-credentials file is stored on its own line as a URL like:

https://<USERNAME>:<PASSWORD>@github.com
Config Username and Password for Different Repositories
Sometimes you may need to use different accounts on the same Git server, for example your company’s corporate account on github.com and your private one.
To be able to configure usernames and passwords for different Git repositories on the same Git server you can enable the useHttpPath option.

By default, Git does not consider the “path” component of an http URL to be worth matching via external helpers. This means that a credential stored for https://example.com/foo.git will also be used for https://example.com/bar.git. If you do want to distinguish these cases, set useHttpPath option to true (source)

Run the following commands to configure Git credentials storage and separate credentials for different repositories on github.com:

$ git config --global credential.helper store
$ git config --global credential.github.com.useHttpPath true
The usernames and passwords for different GitHub repositories will be stored in ~/.git-credentials file separately on their own lines:

https://<USERNAME>:<PASSWORD>@github.com/path/to/repo1.git
https://<USERNAME>:<PASSWORD>@github.com/path/to/repo2.git
Cool Tip: Create a new Git branch and checkout in one command! Read More →
