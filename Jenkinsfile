pipeline {
    agent any

    stages {
        stage('Get Project') {
            steps {
                git branch: 'main', url: 'https://github.com/luke2242/JenkinsTestProject.git'
            }
        }

        stage('build') {
            steps {
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'
            }
        }

        stage('Exec') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }
}
