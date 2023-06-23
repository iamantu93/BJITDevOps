pipeline {
    agent any
parameters {
        string(name: 'PERSON', defaultValue: 'Antu Acharjee', description: 'Who should I say hello to?')
        choice(name: 'DEPARTMENT', choices: ['DevOps', 'Java EE', 'iOS', 'Android'], description: 'Pick a department')

    }
    triggers {
 pollSCM('H/2 * * * *') // Polls the SCM every 2 minutes
 }
tools {
    //maven 'Maven-3.9.1' 
    //jdk 'Jdk-17'
    git 'Default'
}
stages {
    stage('git clone') {
        steps {
            echo 'cloning git repository'
            git branch: 'master', url: 'https://github.com/iamantu93/docker-practice.git'

        } 
    }   
    stage('Build stage') {
        steps {
            script {
                echo 'This is build stage'
                customImage=docker.build('iamantu93/anturepo:jenkins')
                 customImage.push('jenkins')
            }

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
            script {
                kubeconfig(credentialsId: 'kubeconf', serverUrl: '192.168.20.210') {
                    sh '/usr/bin/kubectl apply -f kubedeploy.yml'
                }
            }
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
