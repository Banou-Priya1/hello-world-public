// Environment available

def ENVIRONMENT_LIST = ['cus','prd'] // https://github.com/hove-io/ansible/tree/master/inventories/projects/analytics/


pipeline {
    agent any
    
    parameters {
        choice(name: 'ENVIRONMENT', choices: ENVIRONMENT_LIST, description: 'Env where the playbook will be run')
    }
    
    triggers {
        parameterizedCron('''
            */2 13 * * * %ENVIRONMENT=cus
            */5 13 * * * %ENVIRONMENT=prd
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
