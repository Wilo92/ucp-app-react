pipeline {
    agent any
    tools {
        nodejs 'Node_24' // Configurado en Global Tools
    }
    stages {
        // Etapa 1: Checkout
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/amartinezh/ucp-app-react.git'
            }
        }

        // Etapa 2: Build
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }

        // Etapa 3: Pruebas Paralelizadas
        stage('Pruebas en Paralelo') {
            parallel {
                // Pruebas en Chrome
                stage('Pruebas Chrome') {
                    steps {
                        // Aquí irían los comandos específicos para ejecutar las pruebas en Chrome
                    }
                }

                // Puedes agregar otras pruebas paralelas aquí, por ejemplo:
                // stage('Pruebas Firefox') { steps { ... } }
            }
        }
    }
}
