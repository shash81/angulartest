pipeline {
    agent any
    stages {
        stage('Installing Pahse') {
            steps {
                echo 'Installing npm phase'
                bat 'npm install'
            }
        }
        stage('Sonar Analysis'){
          steps{
            withSonarQubeEnv('LocalSonar') {

            bat '''
            sonar-scanner.bat -D"sonar.projectKey=sample-test"

            '''
            }
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
}
