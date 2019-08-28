pipeline {
    agent { docker { image 'python:3.5.1' } }

    stages {
        stage ('create environment') {
            
            steps{
                sh 'pip install -r requirements.txt'
                 }
            }
        
        stage ('Compile Stage') {
            
            steps{
                sh 'source env/bin/activate && python ./manage.py makemigrations && python ./manage.py migrate'
                 }
            }

        stage ('Testing Stage') {

            steps {
                sh 'source env/bin/activate && python ./manage.py test'
                }
            }
    }
}
