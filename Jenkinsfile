pipeline {
    agent { label 'checkpoint-agent'}
    environment {
    stages{
        stage('Deploy main'){
            when { expression {GIT_BRANCH == 'main'} }
            steps {
                echo "deploy yaml to EKS"
                script {
                // build the image from source Dockerfile + tag it with version
                sh """kubectl apply -f  k8s.yml"""           
                }	
            }
        }

        stage('Build PR'){
            when { expression {GIT_BRANCH =~"PR*"}}
            steps {
                echo "checking with dry run "
                script {
                // build the image from source Dockerfile + tag it with version
                sh """kubectl apply -f k8s.yml --dry-run"""           
                }	
            }	
        }
    }
}