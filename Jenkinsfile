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
            }
        }
        
        stage('Hello2') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
/*
pipeline {
    agent any
    parameters {
      string(name: 'PLANET', defaultValue: 'Earth', description: 'Which planet are we on?')
      string(name: 'GREETING', defaultValue: 'Hello', description: 'How shall we greet?')
    }
    triggers {
        parameterizedCron('''
            # leave spaces where you want them around the parameters. They'll be trimmed.
            # we let the build run with the default name
            */2 * * * * %GREETING=Hola;PLANET=Pluto
            */3 * * * * %PLANET=Mars
        ''')
    }
    stages {
        stage('Example') {
            when {
                triggeredBy 'ParameterizedTimerTriggerCause'
            }
            steps {
                echo 'This build was triggered by a `parameterizedCron` trigger'
            }
        }
    }
}*/
