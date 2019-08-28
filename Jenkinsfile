pipeline {
    agent any

    stages {
        stage ('create environment') {
            sh 'virtualenv env && source env/bin/activate && pip install --upgrade -r requirements.txt'
            }
        
        stage ('Compile Stage') {
            sh 'source env/bin/activate && python ./manage.py makemigrations && python ./manage.py migrate'
            }

        stage ('Testing Stage') {

            steps {
                sh 'source env/bin/activate && python ./manage.py test'
                }
            }
    }
}
