pipeline {
  parameters {
    string(defaultValue: 'xxxxx.py', description: '1st sql', name: 'PYTHON_FILE_1')
    string(defaultValue: 'yyyyy.py', description: '2nd sql', name: 'PYTHON_FILE_2')
  }
  agent {
    node {
      label "docker"
      customWorkspace "workspace/${env.JOB_NAME}"
    }
  }
  stages {
    stage("1st schema select") {
      steps {
        // sh "python ${PYTHON_FILE_1}"
        sh "echo ${PYTHON_FILE_1}"
      }
    }
    stage("2nd schema select") {
      steps {
        // sh "python ${PYTHON_FILE_2}"
        sh "echo ${PYTHON_FILE_2}"
      }
    }
  }
}
