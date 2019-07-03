pipeline {
  parameters {
    string(defaultValue: 'xxxxx.py', description: '1st sql', name: 'PYTHON_FILE_1')
    string(defaultValue: 'yyyyy.py', description: '2nd sql', name: 'PYTHON_FILE_2')
  }
  agent any /*{
    node {
      label "docker"
      customWorkspace "workspace/${env.JOB_NAME}"
    }
  }*/
 stages {
    stage("1st schema select") {
      steps {
        // sh "python ${PYTHON_FILE_1}"
        // sh "echo ${params.PYTHON_FILE_1}"
        sh "python C:/Users/user/PycharmProjects/pygame/plsql/connectsql.py" //本地
        // sh "mysql -h remote:3306 -e select * from abc where date=${PYTHON_FILE_1} and age = ${params.PYTHON_FILE_2}"
        // sh "python abc.py ${PYTHON_FILE_1} ${params.PYTHON_FILE_2}"
      }
    }
    stage("2nd schema select") {
      steps {
        // sh "python ${PYTHON_FILE_2}"
        sh "echo ${params.PYTHON_FILE_2}"
        // sh "python path/aa/bb/sss.py" //本地
        
      }
    }
  }
}
