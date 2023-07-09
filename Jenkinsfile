pipeline {
    agent any

    stages {
        stage('Clonage du dépôt') {
            steps {
                // Cloner le dépôt Git
                git branch: 'master', url: 'https://github.com/amouzougit/jenkins_demo.git'
            }
        }

        stage('Build') {
            steps {
                // Exécuter le build Maven
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Exécuter les tests Maven
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Archiver le package construit
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
