pipeline{
    agent any
    stages{
        stage("Deploy to instance"){
            steps{
                echo "====++++executing Deploy to instance++++===="

                ansiblePlaybook become: true, 
                                disableHostKeyChecking: true, 
                                extras: '-e ENVIROMENT=live -e BRANCH=master', 
                                inventory: 'ansible/deploy/inventory.ini',
                                playbook: 'ansible/deploy/deploy.yml',
                                credentialsId: 'hector.fernandez'
            }
            post{
                success{
                    echo "====++++Deploy to instance executed successfully++++===="
                }
                failure{
                    echo "====++++Deploy to instance execution failed++++===="
                }
        
            }
        }
    }
}