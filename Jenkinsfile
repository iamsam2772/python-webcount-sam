pipeline {
    agent {label 'python' }
    stages {
        stage ('code') {
            steps {
                git branch: "master", 
				url: 'https://github.com/iamsam2772/python-webcount-sam.git'
            }
        }
        stage('build') {
            steps {
                sh "pip install -r requirements.txt",
				sh "tox"
            }
        }
        stage("junit Reports") {
            steps {
                junit '**/junit-39.xml'
            }
        }
    }
}
