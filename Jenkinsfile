// Environment available

def ENVIRONMENT_LIST = ['cus','prd'] // https://github.com/hove-io/ansible/tree/master/inventories/projects/analytics/


pipeline {
    agent any
    
    parameters {
        choice(name: 'ENVIRONMENT', choices: ENVIRONMENT_LIST, description: 'Env where the playbook will be run')
    }
    
    triggers {
        parameterizedCron('''
            25 15 * * * %ENVIRONMENT=cus
        ''')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo $ENVIRONMENT
            }
        }
        
        stage('Hello2') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
