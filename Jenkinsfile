pipeline {
  agent any
  tools{
    maven 'maven-3.9.0'
  }
  stages{
    stage('Checkout')
    {
      steps{
        git branch: 'master' ,url: 'https://github.com/ShalabhRanjan19/shalabhansible.git'
      }
    }
    stage('Run')
    {
      steps{
        sh 'mvn clean install'
      }
    }
    stage('test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Deployment')
    {
      steps{
        sh 'ansible-playbook ansible/playboook.yml -i ansible/hosts.ini'
      }
    }
  }
}
