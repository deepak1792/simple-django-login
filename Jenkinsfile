pipeline {
    agent any

    stages {
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
