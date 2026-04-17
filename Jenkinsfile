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
                dir('JenkinsTestProject') {
                    sh 'mvn clean'
                    sh 'mvn dependency:copy-dependencies'
                    sh 'mvn compile'
                }
            }
        }

        stage('Exec') {
            steps {
                dir('JenkinsTestProject') {
                    sh 'mvn exec:java'
                }
            }
        }
    }
}
