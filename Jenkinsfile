// Environment available

def ENVIRONMENT_LIST = ['cus','prd'] // https://github.com/hove-io/ansible/tree/master/inventories/projects/analytics/


pipeline {
    agent any
    
    parameters {
        choice(name: 'ENVIRONMENT', choices: ENVIRONMENT_LIST, description: 'Env where the playbook will be run')
    }
    
    triggers {
        parameterizedCron('''
            15 17 * * * %ENVIRONMENT=cus
            17 17 * * * %ENVIRONMENT=prd
            14 17 * * * %ENVIRONMENT=cus
            18 17 * * * %ENVIRONMENT=prd
            21 17 * * * %ENVIRONMENT=cus
            25 17 * * * %ENVIRONMENT=prd
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
