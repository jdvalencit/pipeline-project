pipeline(
    agent{
        label "jenkins-agent"
    }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage('Cleanup Workspace'){
            steps{
                cleanWs()
            }
        }

        stage('Checkout from SCM'){
            steps{
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/jdvalencit/pipeline-project.git'
            }
        }

        stage('Build Application'){
            steps{
                sh "nvm clean package"
            }
        }

        stage('Test Application'){
            steps{
                sh "nvm test"
            }
        }
    }
)