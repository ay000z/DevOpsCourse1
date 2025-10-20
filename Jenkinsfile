pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Compile code') {
            steps {
                sh '''
                    # Utiliser le chemin absolu pour éviter les problèmes de PATH
                    /usr/lib/jvm/java-21-openjdk-amd64/bin/javac -d . src/application/Test.java
                    echo "✅ Compilation réussie!"
                    ls -la application/
                '''
            }
        }
        stage('Execute code') {
            steps {
                sh '''
                    /usr/lib/jvm/java-21-openjdk-amd64/bin/java application.Test
                '''
            }
        }
        stage('Success Message') {
            steps {
                echo '🎉 Pipeline exécuté avec succès!'
            }
        }
    }
}
