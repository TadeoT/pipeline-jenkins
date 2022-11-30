pipeline{
    agent {label 'linux-master' }
    stages{
        stage('paso-1'){
            steps{
                script{
                    sh "echo 'hello world'"
                    sh 'java --version'
                }
            }
        }
    }
    post{
        always {
            deleteDir()
            sh "echo 'fase alwaws'"
        }
        success{
            sh "echo 'fase success'"
        }
        failure{
            sh "echo 'fase failure'"
            mail to: "ttiraboschi@santafe.gov.ar", body: "$JOB_URL",subject: "[Jenkins] $JOB_BASE_NAME: Ejecución $BUILD_NUMBER fallida"
        }
        
    }
}
