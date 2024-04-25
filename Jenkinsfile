pipeline{
    agent {
        node{
            label 'Agent-1'
        }
    }

    environment{
        GREETING = 'Hello Jenkins'
    }
    options{
        timeout(time: 1, unit:'HOURS')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage("Build"){
            steps{
            echo 'Building'
            }
        }
        stage("test"){
            steps{
            echo 'Testing'
            }
        }
        
        stage('Deploy'){
            steps{
                echo 'Deploy'
            }
        }
        stage('check'){
            steps{
                sh """
                echo "Here i wrote shell script"
                echo $GREETING
                """

            }
        }

        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }

    post{
        always{
            echo 'I will always say Hello again'
        }
        failure{
            echo 'this runs when pipeline is failed, used to send some alerts '
        }
        success{
            echo 'i will say Hello if pipeline success '
        }
    }
    
}