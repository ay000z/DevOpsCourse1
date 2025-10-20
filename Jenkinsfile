pipeline {
    agent any
    tools {
        jdk 'JDK21'
    }
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Compile code') {
            steps {
                sh 'javac -d . src/application/Test.java'
            }
        }
        stage('Execute code') {
            steps {
                sh 'java application.Test'
            }
        }
        stage('Success Message') {
            steps {
                echo '🎉 Pipeline exécuté avec succès depuis Jenkinsfile!'
                echo "Branch: ${env.GIT_BRANCH}"
                echo "Commit: ${env.GIT_COMMIT}"
            }
        }
    }
}
