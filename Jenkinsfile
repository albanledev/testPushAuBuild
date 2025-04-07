pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                // Nettoyer le répertoire existant si nécessaire
                sh 'rm -rf testPushAuBuild'
                
                // Cloner le repository
                sh 'git clone https://github.com/albanledev/testPushAuBuild.git'
                
                // Vérifier le contenu après le clonage
                sh 'ls -R'
            }
        }
        
        stage('build') {
            steps {
                sh 'cd testPushAuBuild && javac Main.java'
            }
        }
        
        stage('run') {
            steps {
                script {
                    sh "cd testPushAuBuild && java Main "
                }
            }
        }
    }
}
