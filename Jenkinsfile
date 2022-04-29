pipeline {
    agent any
    triggers {
        parameterizedCron('''
            30 15 * * * 
        ''')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('Hello2') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
