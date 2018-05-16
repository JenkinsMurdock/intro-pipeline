pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
        echo "Hello, ${MY_NAME}!"
        echo "Hello ${params.Name}!"
        sh 'java -version'
      }
    }
  }
  environment {
    MY_NAME = 'Dave'
    TEST_USER = credentials('test-user')
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'
      
    }
    
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}