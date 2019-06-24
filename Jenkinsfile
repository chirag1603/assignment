pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'java'
    }
    stages{
        stage('Clone sources'){
            steps{
                git url: 'https://github.com/spring-projects/spring-petclinic.git'
            }
        }
        stage('Build'){
            steps{
            sh 'mvn clean compile test install'
            }
        }
        stage('Deploy'){
            steps{
            dir('/mnt/artificat') {
                archiveArtifacts '*.jar'
            }
            }
        }
    }

