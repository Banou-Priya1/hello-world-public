// Environment available

def ENVIRONMENT_LIST = ['cus','prd'] // https://github.com/hove-io/ansible/tree/master/inventories/projects/analytics/
def LOAD_LIST = ['stat','referential','disruption','subscription']

pipeline {
    agent any
    
    parameters {
        choice(name: 'ENVIRONMENT', choices: ENVIRONMENT_LIST, description: 'Env where the playbook will be run')
        choice(name: 'LOAD', choices: LOAD_LIST, description: 'Choose load value')
        
    }
    
    triggers {
        parameterizedCron('''
            26 17 * * * %ENVIRONMENT=cus %LOAD=stat
            18 17 * * * %ENVIRONMENT=prd %LOAD=referential
            30 17 * * * %ENVIRONMENT=cus %LOAD=referential
            31 17 * * * %ENVIRONMENT=prd %LOAD=stat
            33 17 * * * %ENVIRONMENT=cus %LOAD=stat
            35 17 * * * %ENVIRONMENT=prd %LOAD=referential
        ''')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo "${params.ENVIRONMENT}"
            }
        }
        
        stage('Hello2') {
            steps {
                echo 'Hello World'
                echo "${params.ENVIRONMENT}"
            }
        }
    }
}
