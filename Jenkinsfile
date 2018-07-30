pipeline {
    agent {
        label 'linux'
    }
    tools {
        maven 'maven-3.5.4'
    }
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/dreamer-nitj/myjenkinsproject'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clear compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
