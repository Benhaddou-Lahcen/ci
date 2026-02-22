pipeline {
    agent any

    tools {
        // Doit correspondre au nom 'Maven' dans tes outils Jenkins
        maven 'Maven' 
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Récupération du code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Compilation du projet...'
                sh 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                echo 'Exécution de l\'application...'
                sh 'mvn exec:java -Dexec.mainClass="me.lahcen.App"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline terminé avec succès !'
        }
    }
}
