pipeline{
    agent any
    stages{
        stage("Deploy to instance"){
            steps{
                echo "====++++executing Deploy to instance++++===="

                ansiblePlaybook become: true, 
                                colorized: true, 
                                disableHostKeyChecking: true, 
                                extras: 'ENVIROMENT=live, BRANCH=master', 
                                forks: 2, 
                                inventory: 'ansible/inventory.ini',
                                playbook: 'ansible/deploy.yml', 
                                sudoUser: null, 
                                vaultCredentialsId: 'id_ed25519'
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