pipeline {
    agent { label 'agent4' }
    stages {
        stage('Build'){
            steps {
                script {
                    sh """
                    echo "Hello sai this is the stage1 in pipeline"
                    """
                }
            }
        }
        stage('Test'){
            steps {
                script {
                    sh """
                    echo "This is the stage 2 in the pipeline"
                    """
                }
            }
        }
        stage('Deploy'){
            steps {
                script {
                    sh """
                    echo "Hello this is the stage 3 in the pipeline"
                    """
                }
            }
        }
    post {
        always {
            echo "Always run"
        }
        failure {
            echo "failure occurs"
        }
        success {
            echo "success occurs"
        }
    }
    }
}


// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 //
//             }
//         }
//         stage('Test') {
//             steps {
//                 //
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 //
//             }
//         }
//     }
// }