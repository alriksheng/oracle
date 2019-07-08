pipeline {
  parameters {
    string(defaultValue: 'executeCall.py', description: 'PYTHON_FILE', name: 'PYTHON_FILE')
    string(defaultValue: 'checkResult.py', description: 'PYTHON_FILE2', name: 'PYTHON_FILE_2')
    string(defaultValue: 'executeCall.sql', description: 'SQL_FILE', name: 'SQL_FILE')
    string(defaultValue: 'C:/Users/user/PycharmProjects/pygame/plsql', description: 'FILE_PATH_PY', name: 'FILE_PATH_PY')
    string(defaultValue: 'D:/pyoracle', description: 'FILE_PATH_SQL', name: 'FILE_PATH_SQL')
    string(defaultValue: '20190701', description: 'DATA_d1', name: 'DATA_d1')
    string(defaultValue: '20190702', description: 'DATA_d2', name: 'DATA_d2')
    string(defaultValue: '20190703', description: 'DATA_d3', name: 'DATA_d3')
    string(defaultValue: '20190704', description: 'DATA_d4', name: 'DATA_d4')
    string(defaultValue: '20190705', description: 'DATA_d5', name: 'DATA_d5')
    string(defaultValue: '20190706', description: 'DATA_d6', name: 'DATA_d6')
    string(defaultValue: '20190707', description: 'DATA_d7', name: 'DATA_d7')
    string(defaultValue: '20190701', description: 'DATA_mth', name: 'DATA_mth')
  }
  agent any /*{
    node {
      label "docker"
      customWorkspace "workspace/${env.JOB_NAME}"
    }
  }*/
 stages {
   
    stage("2nd schema check") {
      steps {
        // execute
        sh "python ${params.FILE_PATH_PY}/${params.PYTHON_FILE2}" //本地
      }
    }
  }
}
