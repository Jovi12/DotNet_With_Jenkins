pipeline{
    agent any
    
    stages{
        stage("git pull"){
            steps{
                git 'https://github.com/Jovi12/DotNet_With_Jenkins'
            }
        }
        stage("build"){
            steps{
                bat 'dotnet restore'
                bat 'dotnet build --no-restore'
                echo "done"
            }
        }
        stage("docker build"){
            steps{
                bat 'docker build -t dotjenimage .'
                echo 'build finished'
            }
        }
        stage("docker image run"){
            steps{
                bat ' docker run -d -p 8081:8080 dotjenimage'
                echo 'docker image running'
            }
        }
    }
}