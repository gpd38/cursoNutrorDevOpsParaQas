# Aula2

Nesta aula iremos falar sobre o jenkins. 

<table>
	<tr>
		<td align="center">
			<img style="border-radius: 50%;" src="https://github.com/gpd38/cursoNutrorDevOpsParaQas/blob/main/img/aula2-jenkins.png" width="100px;" alt=""/>
			<br /><b>Layout do Jenkins</b>
		</td>
	</tr>
</table>

Jenkins é um servidor de automação que ajuda as partes do desenvolvimento de software relacionadas à construção, teste e implantação, facilitando a integração e entrega contínuas.

Link de acesso: [Download Jenkins utilizado](https://get.jenkins.io/war/2.289/jenkins.war)

## Mão na massa

Abra o prompt de comando na pasta onde o arquivo está localizado.

Execute o comando:
```
java -jar jenkins.war
```

Após o término da instalação, copiar a senha disponibilizada no prompt de comando para prosseguir nos próximos passos.

<table>
	<tr>
		<td align="center">
			<img style="border-radius: 50%;" src="https://github.com/gpd38/cursoNutrorDevOpsParaQas/blob/main/img/senha.png" width="100px;" alt=""/>
			<br /><b>Senha informada no prompt</b>
		</td>
	</tr>
</table>

## Passo: Configuração

* Para acessar o jenkins e iniciar a configuração digite no seu navegador a url localhost:8080.
* Informe a senha disponibilizada na instalação do jenkins.
* Instale os plugins sugeridos.
* Criar um usuário de acesso ao jenkins.

## Passo: Criar projeto

Existe várias configurações que podem ser utilizadas. Neste projeto utilizaremos somente a opção de executar shell, ou seja, linha de comando.

### Projeto Free-style

* Escolha o projeto "free-style";
* Aba 4: Ambiente de build para o ambiente windows;
* Inserir os comandos que deseja testar, por exemplo: "mvn -version", "mvn install", "git status";
* Salvar e construir o projeto;

### Projeto Pipeline

* Escolha o projeto "pipeline";
* Aba 3: Advanced project options;
* Inserir o script do pipeline que você deseja testar, por exemplo:

```script
pipeline{
	agent any

	stages{
		stage('Maven version'){
			steps{
				bat "mvn -version"
			}
		}
		stage('Git'){
			steps{
				git 'https://github.com/user/projeto.git'
			}
		}
		stage('Test'){
			steps{
				bat "mvn install"
			}
		}
	}
}
```
* Salvar e construir o projeto;