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
                dir('CT209_Lab5TestProject') {
                    sh 'mvn clean'
                    sh 'mvn dependency:copy-dependencies'
                    sh 'mvn compile'
                }
            }
        }

        stage('package') {
            steps {
                dir('CT209_Lab5TestProject') {
                    sh 'mvn package'
                }
            }
        }

        stage('Exec') {
            steps {
                dir('CT209_Lab5TestProject') {
                    sh 'mvn exec:java'
                }
            }
        }
    }
}
