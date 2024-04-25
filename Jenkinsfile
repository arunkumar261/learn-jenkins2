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
    
}