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
            sonar-scanner.bat -D"sonar.projectKey=angular-test" -D"sonar.sources=." -D"sonar.host.url=http://localhost:9000" -D"sonar.login=752a1fb929ef94813d2748e87dfda41305784232"

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
