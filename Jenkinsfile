pipeline {
    agent { label 'agent' }
    stages {
        stage('build') {
            steps {
                script {
                    sh   """
                        docker build -t gcr.io/m7mxoxd/final_project .
                        docker push gcr.io/m7mxoxd/final_project
                    """
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    sh    """
                        kubectl apply -f Deployment
                    """
                }
            }
        }
    }
}