pipeline {
    agent { label 'slave-node' }
parameters {
        string(name: 'PERSON', defaultValue: 'Antu Acharjee', description: 'Who should I say hello to?')
        choice(name: 'DEPARTMENT', choices: ['DevOps', 'Java EE', 'iOS', 'Android'], description: 'Pick a department')

    }
tools {
    maven 'Maven-3.9.1' 
    jdk 'Jdk-17'
    git 'git-2.40'
}
stages {
    stage('git clone') {
        steps {
            echo 'cloning git repository'
            git branch: 'main', url: 'https://github.com/antu-acharjee/git-exam.git'

        } 
    }   
    stage('Build stage') {
        steps {
            echo 'This is build stage'

        } 
    }
    stage('Script execute') {
        steps {
            echo 'This is Script execute stage'
           
            bat 'antu.bat' 
        } 
    }
    stage('Test stage') {
        steps {
            echo 'This is Test stage'
        } 
    }
    stage('Deploy stage') {
        steps {
            echo 'This is deploy stage'
        } 
    }
 }
post { 
    success { 
        echo 'Status is green'
        echo "successfully built and deployed by ${PERSON}"
        echo "A proud ${DEPARTMENT} engineer"
    }

    failure{
        echo 'Status is red'
    }

    unstable{
        echo "Build is unstable"
    }
}
}