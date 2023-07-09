pipeline {
    agent any

    stages {
        stage('Clonage du dépôt') {
            steps {
                git branch: 'master', url: 'https://github.com/amouzougit/jenkins_demo.git'
            }
        }

        stage('Build et test') {
            steps {
                bat 'mvn clean package'
                bat 'mvn test'
            }
        }

        stage('Archiver les artefacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
