pipeline {
    agent { label 'agent4' }
    environment {
        PROJECT = 'Expense'
        SERVICE = 'Bhp'
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 30, unit: 'MINUTES')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build'){
            steps {
                script {
                    sh """
                    echo "Hello sai this is the stage1 in pipeline"
                    echo "project: $PROJECT"
                    echo "Hello ${params.PERSON}"
                    echo "Hello ${params.BIOGRAPHY}
                    echo "Hello ${params.TOGGLE}
                    echo "Hello ${params.CHOICE}
                    echo "Hello ${params.PASSWORD}
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
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                script {
                    sh """
                    echo "Hello this is the stage 3 in the"
                    """
                }
            }
        }
    }
    post {
        always {
            echo 'always shows'
        }
        failure {
            echo 'failure occurs'
        }
        success {
            echo 'success occurs'
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