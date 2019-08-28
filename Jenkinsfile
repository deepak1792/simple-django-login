pipeline {
    agent { docker { image 'python:3.6' } }

    stages {
        stage ('create environment') {
            
            steps{
                    git deepak1792: 'yadav9412543763', url: 'https://github.com/deepak1792/simple-django-login.git'
                 }
            }
        stage ('create environment') {
            
            steps{
                sh 'virtualenv -p python3.6 venv'
                sh 'source venv/bin/activate'
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
