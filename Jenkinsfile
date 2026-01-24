pipeline {
    agent any

    stages {
        stage('Checkout Test') {
            steps {
                echo 'Repository fetched successfully'
            }
        }

        stage('Pipeline Test') {
            steps {
                echo 'Jenkins Pipeline is working'
            }
        }
       stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat '''
                    sonar-scanner ^
                    -Dsonar.projectKey=squ_43c71329a40b948fd2e855ae17bacb179aa37c3c ^
                    -Dsonar.projectName=SonarQube ^
                    -Dsonar.sources=.
                    '''
                }
            }
        }
    }
}
