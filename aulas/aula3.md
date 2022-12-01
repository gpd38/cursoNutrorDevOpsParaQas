# Aula3

Iremos criar um pipeline para o projeto atual que utiliza a API do PetStore.

## Mão na massa

* Criar o projeto pipeline no Jenkins;
* Aba 3: Advanced project options;
* Inserir o script do pipeline:

```script
pipeline{
	agent any

	stages{
		stage('Iniciar o container'){
			steps{
				bat "docker start id_container"
			}
		}
		stage('Baixar o projeto'){
			steps{
				git 'https://github.com/user/projeto.git'
			}
		}
		stage('Executar os testes'){
			steps{
				bat "mvn test"
			}
		}
		stage('Parar o container'){
			steps{
				bat "docker stop id_container"
			}
		}
	}
}

```
