pipeline {
    agent any
    stages {
        stage('Installing Pahse') {
            steps {
                echo 'Installing npm phase'
                bat 'npm install'
            }
        }
        stage('Lint Pahse') {
            steps {
                echo 'Installing npm phase'
                bat 'npm run lint'
            }
        }
        stage('npm build production') {
            steps {
                echo 'building npm phase'
                bat 'npm run build --production'
              //  bat 'xcopy /s /i /y "%WORKSPACE%\dist\angulartest" "C:\Apache24\htdocs\" '
            }
        }
         stage('moving dist folder') {
            steps {
                echo 'moving dist folder'               
               // bat ' xcopy /s /i /y "%WORKSPACE%/dist/angulartest" "C:/Apache24/htdocs/" '
            }
        }
    }
    post {
    always {
        echo 'always execute...'
        // cleanWs() clean up our workspace
    }
    success {
        echo 'Succeeded'
        slackSend (color: '#BDFFC3', message: "pipeline build succeeded")
    }
    unstable {
        echo 'Unstable'
        slackSend (color: '#FFFE89', message: "pipeline build unstable")
    }
    failure {
        echo 'Failed'
        slackSend (color: '#FF9FA1', message: "pipeline build failed")
    }
  }
}