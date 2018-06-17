
pipeline {
	agent any   
	stages {
		stage('Preparacion') { // for display purposes
		      // Get some code from a GitHub repository
		      steps {
				git 'https://github.com/masterunir17/appmaster.git'
				}		
		   }
		stage('Compilar') { // Genera los ficheros .class con los fuentes .java
			steps {
			sh 'mvn compile'
			     	}			
			}
		stage('Test') { // Ejecuta los comandos de JUnt - Pruebas unitarias
			steps {
			sh 'mvn test'
			}		     
		    }
		stage('Empaquetado') { // Crear el .Jar validado
			steps {
				sh 'ssh root@172.31.57.100 mkdir -p /var/www/temp_deploy'
				sh 'scp -r /var/lib/jenkins/workspace/pipetest1/aplicacion/* root@172.31.57.100:/var/www/temp_deploy/'
			   
			}		     
		    }
		}

	}
