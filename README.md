# vsCode for Python Developers

Estudo de PI fazendo uso do treinamento Linkedin Learning, vsCode for Python Developers

## Autenticação do repositório Github no vsCode Editor

Uma dificuldade que o estudante pode encontrar é autenticar a contado Github no vsCode, para isso o mesmo pode fazer uso
das dicas encontradas no blog abaixo ou no video de youtube que explica essa questão muito bem.

Eu criei um Token para autenticação do repositório no vsCode localmente na minha máquina, mas outras formas de autenticação
são permitidas.

Vou deixar o texto original em inglês da postagem.

[Dicas de como autenticar a conta Github](https://www.shellhacks.com/git-config-username-password-store-credentials/)

**Git – Config Username & Password – Store Credentials** Posted on July 19, 2019by admin
To connect to a Git repository with authentication over HTTP(S), every time it needs to set a username and password.

You can configure Git to remember a username and password by storing them in a remote URL or by using Git credential helper.

In this article i am showing how to clone Git repository by setting a username and password on the command line, how to save a username and password in Git credentials storage and how to configure different usernames and passwords for different repositories on the same Git server.

Cool Tip: Show Git branch name in the command prompt! Read more →

Warning: Your Git credentials will be saved in a plaintext format in the files .git/config or ~/.git-credentials, depending on the method you choose.

Set Username and Password in Remote URL
To save credentials you can clone Git repository by setting a username and password on the command line:

$ git clone https://<USERNAME>:<PASSWORD>@github.com/path/to/repo.git
The username and password will be stored in .git/config file as a part of the remote repository URL.

If you have already cloned a repository without setting username and password on the command line, you can always update the remote URL by running the following command:

$ git remote set-url origin https://<USERNAME>:<PASSWORD>@github.com/path/to/repo.git
Save Username and Password in Git Credentials Storage
Run the following command to enable credentials storage in your Git repository:

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
