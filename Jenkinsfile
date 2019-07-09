pipeline {
  parameters {
    string(defaultValue: 'executeCall.py', description: 'PYTHON_FILE', name: 'PYTHON_FILE')
    string(defaultValue: 'executeCall.sql', description: 'SQL_FILE', name: 'SQL_FILE')
    string(defaultValue: 'executeCall1.sql', description: 'SQL_FILE_TEMP', name: 'SQL_FILE_TEMP')
    string(defaultValue: 'C:/Users/user/PycharmProjects/pygame/plsql', description: 'FILE_PATH', name: 'FILE_PATH')
    string(defaultValue: '20190711', description: 'DATA_1', name: 'DATA_1')
    //string(defaultValue: '20190713', description: 'DATA_2', name: 'DATA_2')
  }
  agent any 
 stages {
    stage("1st schema executeCall") {
      steps {
        // powershell
        sh "(Get-Content ${params.FILE_PATH}/${params.SQL_FILE_TEMP}) | ForEach-Object {$_ .replace 'DATA_1','${params.DATA_1}'} | Set-Content ${params.FILE_PATH}/${params.SQL_FILE}"
        // execute
        sh "python ${params.FILE_PATH}/${params.PYTHON_FILE}" //本地
      }
    }
  }
}
