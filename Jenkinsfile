// Environment available

def ENVIRONMENT_LIST = ['cus','prd'] // https://github.com/hove-io/ansible/tree/master/inventories/projects/analytics/


pipeline {
    agent any
    
    parameters {
        choice(name: 'ENVIRONMENT', choices: ENVIRONMENT_LIST, description: 'Env where the playbook will be run')
    }
    
    triggers {
        parameterizedCron('''
            H(45-46) 16 * * * %ENVIRONMENT=cus
            H/5 16 * * * %ENVIRONMENT=prd
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
