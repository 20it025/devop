

pipeline {
    agent any
    
    stages {
        stage('build') {
            
            steps {
                echo 'building the application'
                //echo "Software version is ${NEW_VERSION}"
            }
        }
      stage('test') {
          //when{
          //    expression{
          //        env.BRANCH_NAME == 'dev'
          //    }
          //}
            steps {
                echo 'testing the application'
            }
        }
      stage('deploy') {
            steps {
                echo 'deplying the application'
                // sh 'wrong command'
                //echo "${SERVER_CREDENTIALS}"
                withCredentials([
                    usernamePassword(credentials: 'docker', usernameVariable : USERNAME, passwordVariable : PASSWORD)
                ]){
                    //echo "user is ${USERNAME}"
                }
            }
        }
    }
    post{
        always{
            echo 'Executing always'
        }
        success{
            echo 'Executing success'
        }
        failure{
            echo 'Executing failure'
        }
    }
}
