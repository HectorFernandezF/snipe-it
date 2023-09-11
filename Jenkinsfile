pipeline{
    agent any
    stages{
        stage("Deploy to instance"){
            steps{
                echo "====++++executing Deploy to instance++++===="
                ansiblePlaybook become: true, inventory: 'ansible/inventory.ini', playbook: 'ansible/deploy.yml'
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