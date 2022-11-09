pipeline {
    agent any
    stages{
        stage('Github-Checkout'){
            steps{
//                git 'https://github.com/simplilearn-github/Pipeline_Script.git';
                echo "Github Repositories has been loaded Successfully!";
            }
        }
        stage('Build'){
            steps{
                bat 'Build.bat';
                echo "Build bat loaded Successfully!";
            }
        }

        stage('JUnit'){
            steps{
                bat 'Unit.bat';
                echo "Junit test passed Successfully!";
            }
        }
        stage('Quality-Gate'){
            steps{
                bat 'Quality.bat';
                echo "SonarQube quality passed Successfully!";
            }
        }

        stage('Deploy'){
            steps{
                bat 'Deploy.bat';
                echo "Deployed Successfully!";
            }
        }

    }

    post{
        always{
            echo "This will always run";
        }
        success{
            echo "This will run only if succeed";
        }
        failure{
            echo "This will run only if failed";
        }
        unstable{
            echo "This will run only if the run was marked as unstable";
        }
        changed{
            echo "This will run only if state of pipeline changed";
            echo "for example if the pipeline was previously failed but it now successful";
        }
    }
}/
