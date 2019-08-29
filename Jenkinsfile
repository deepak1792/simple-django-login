pipeline {
    agent { docker { image 'python:3.6' } }

    stages {
       
        stage ('Checkout') {
           
            steps{
                git branch: 'master',
                credentialsId: '79cea412-cbec-4d63-b91e-61fd616f0a46',
                url: 'https://github.com/deepak1792/simple-django-login.git'
                sh "ls -lat"
                 }
            }
   
        stage ('install req') {
           
            steps{
                withEnv(["HOME=${env.WORKSPACE}"]){
                sh 'python -m pip install django==1.9.7 --user'
                }
              }
            }
       
       
        stage ('Compile Stage') {
           
            steps{
                withEnv(["HOME=${env.WORKSPACE}"]){
                sh 'python manage.py makemigrations && python manage.py migrate'
                }
                 }
            }

        stage ('Testing Stage') {

            steps {
                withEnv(["HOME=${env.WORKSPACE}"])
                {
                sh 'python manage.py test'
                }
                }
            }
        stage ('Run server') {

            steps {
                withEnv(["HOME=${env.WORKSPACE}"])
                {
                sh 'python manage.py runserver'
                }
                }
            }
    }
}
