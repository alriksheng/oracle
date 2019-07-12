pipeline {
  parameters {
    string(defaultValue: 'executeCall.py', description: 'PYTHON_FILE', name: 'PYTHON_FILE')
    string(defaultValue: 'checkResult.py', description: 'PYTHON_FILE2', name: 'PYTHON_FILE2')
    string(defaultValue: 'executeCall.sql', description: 'SQL_FILE', name: 'SQL_FILE')
    string(defaultValue: 'executeCall1.sql', description: 'SQL_FILE_TEMP', name: 'SQL_FILE_TEMP')
    string(defaultValue: 'C:/Users/user/PycharmProjects/pygame/plsql', description: 'FILE_PATH_PY', name: 'FILE_PATH_PY')
    string(defaultValue: 'D:/pyoracle', description: 'FILE_PATH_SQL', name: 'FILE_PATH_SQL')
    string(defaultValue: '20190701', description: 'DATA_d1', name: 'DATA_d1')
    //string(defaultValue: '20190702', description: 'DATA_d2', name: 'DATA_d2')
    //string(defaultValue: '20190703', description: 'DATA_d3', name: 'DATA_d3')
    //string(defaultValue: '20190704', description: 'DATA_d4', name: 'DATA_d4')
    //string(defaultValue: '20190705', description: 'DATA_d5', name: 'DATA_d5')
    //string(defaultValue: '20190706', description: 'DATA_d6', name: 'DATA_d6')
    //string(defaultValue: '20190707', description: 'DATA_d7', name: 'DATA_d7')
    string(defaultValue: '20190701', description: 'DATA_mth', name: 'DATA_mth')
  }
  agent any 
  stages {
    stage("1st schema call") {
      steps {
        script{
          // to int
          def data_d1_int
          data_d1_int = ${params.DATA_d1} as Integer
          data_d2_int = data_d1_int + 1
          data_d3_int = data_d1_int + 2
          data_d4_int = data_d1_int + 3
          data_d5_int = data_d1_int + 4
          data_d6_int = data_d1_int + 5
          data_d7_int = data_d1_int + 6
          // to string
          data_d2_str = data_d2_int as String
          data_d3_str = data_d2_int as String
          data_d4_str = data_d2_int as String
          data_d5_str = data_d2_int as String
          data_d6_str = data_d2_int as String
          data_d7_str = data_d2_int as String
          // powershell
          sh "Get-Content ${params.FILE_PATH_SQL}/${params.SQL_FILE_TEMP} | ForEach-Object {\$_ -replace ('DATA_d1','${params.DATA_d1}') -replace ('DATA_d2', '${data_d2_str}')}| Set-Content ${params.FILE_PATH_SQL}/${params.SQL_FILE}"
        }
         // execute
        //sh "python ${params.FILE_PATH_PY}/${params.PYTHON_FILE}" //本地
      }
    } 
    /*stage("2nd schema check") {
      steps {
        // execute
        sh "python ${params.FILE_PATH_PY}/${params.PYTHON_FILE2}" //本地
      }
    }*/
  }
}
