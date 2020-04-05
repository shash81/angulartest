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
                bat 'xcopy /s /i /y "%WORKSPACE%\dist\angulartest" "C:\Apache24\htdocs\" '
            }
        }
         stage('moving dist folder') {
            steps {
                echo 'moving dist folder'               
                bat 'xcopy /s /i /y "%WORKSPACE%\dist\angulartest" "C:\Apache24\htdocs\" '
            }
        }
    }
}