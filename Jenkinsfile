pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/Yuri2021/jenops.git', branch: 'main'
            }
        }

        stage('Update app.py') {
            steps {
                script {
                    def appFile = readFile('app.py')
                    appFile = appFile.replace('Hello, World!', 'Hello, World Update!')
                    writeFile file: 'app.py', text: appFile
                }
            }
        }

        stage('Commit Changes') {
            steps {
                sh 'git config user.email "sladkev_yu@hotmail.com"'
                sh 'git config user.name "Yuri2021"'
                sh 'git add app.py'
                sh 'git commit -m "Updated Hello, World! to Hello, World Update!"'
                sh 'git push origin main'
            }
        }
    }
}
