pipeline{
    agent {
        node{
            label 'Agent-1'
        }
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