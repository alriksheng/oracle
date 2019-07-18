pipeline {
  parameters {
    string(defaultValue: 'executeCall.py', description: 'PYTHON_FILE', name: 'PYTHON_FILE')
    string(defaultValue: 'checkResult.py', description: 'PYTHON_FILE2', name: 'PYTHON_FILE2')
    string(defaultValue: 'step2.sql', description: 'SQL_FILE', name: 'SQL_FILE')
    string(defaultValue: 'step2_temp.sql', description: 'SQL_FILE_TEMP', name: 'SQL_FILE_TEMP')
    string(defaultValue: 'checkResult_step2.sql', description: 'SQL_FILE2', name: 'SQL_FILE2')
    string(defaultValue: 'checkResult_step2_temp.sql', description: 'SQL_FILE_TEMP2', name: 'SQL_FILE_TEMP2')
    string(defaultValue: 'C:/Users/user/PycharmProjects/pygame/plsql', description: 'FILE_PATH_PY', name: 'FILE_PATH_PY')
    string(defaultValue: 'D:/pyoracle', description: 'FILE_PATH_SQL', name: 'FILE_PATH_SQL')
    string(defaultValue: '20190701', description: 'DATA_d1', name: 'DATA_d1')
    string(defaultValue: '20190701', description: 'DATA_mth', name: 'DATA_mth')
    string(defaultValue: '10.161.97.183:1521/orcl', description: 'DATABASENAME_183', name: 'DATABASENAME_183')
    string(defaultValue: 'C##FAST183', description: 'USERNAME_183', name: 'USERNAME_183')
    string(defaultValue: '192.168.61.161:1521/FAST', description: 'DATABASENAME_161', name: 'DATABASENAME_161')
    string(defaultValue: 'fast', description: 'USERNAME_161', name: 'USERNAME_161')
  }
  agent any 
  stages {
    stage("1st schema call") {
      steps {
        script{
          // to int
          def data_d1_int = params.DATA_d1 as Integer
          data_d2_int = data_d1_int + 1
          data_d3_int = data_d1_int + 2
          data_d4_int = data_d1_int + 3
          data_d5_int = data_d1_int + 4
          data_d6_int = data_d1_int + 5
          data_d7_int = data_d1_int + 6
          // to string
          data_d2_str = data_d2_int as String
          data_d3_str = data_d3_int as String
          data_d4_str = data_d4_int as String
          data_d5_str = data_d5_int as String
          data_d6_str = data_d6_int as String
          data_d7_str = data_d7_int as String
          // powershell
          powershell "Get-Content ${params.FILE_PATH_SQL}/${params.SQL_FILE_TEMP} | ForEach-Object {\$_ -replace ('DATA_d1','${params.DATA_d1}') -replace ('DATA_d2', '${data_d2_str}') -replace ('DATA_d3','${data_d3_str}') -replace ('DATA_d4','${data_d4_str}') -replace ('DATA_d5','${data_d5_str}') -replace ('DATA_d6','${data_d6_str}') -replace ('DATA_d7','${data_d7_str}') -replace ('DATA_mth','${params.DATA_mth}')}| Set-Content ${params.FILE_PATH_SQL}/${params.SQL_FILE}"

        }
                // execute
        //sh "python ${params.FILE_PATH_PY}/${params.PYTHON_FILE} ${params.FILE_PATH_SQL}/${params.SQL_FILE} ${params.USERNAME_183} ${params.DATABASENAME_183}" //本地
      }
    } 
    stage("2nd schema check") {
      steps {
        script{
          // to int
          def data_d1_int = params.DATA_d1 as Integer
          mth_end_int = data_d1_int + 29
          // to string
          mth_end_str = mth_end_int as String
          // powershell
          powershell "Get-Content ${params.FILE_PATH_SQL}/${params.SQL_FILE_TEMP2} | ForEach-Object {\$_ -replace ('DATA_mth','${params.DATA_mth}') -replace ('mth_end', '${mth_end_str}') }| Set-Content ${params.FILE_PATH_SQL}/${params.SQL_FILE2}"

        }
        // execute
        //sh "python ${params.FILE_PATH_PY}/${params.PYTHON_FILE2} ${params.FILE_PATH_SQL}/${params.SQL_FILE2} ${params.USERNAME_183} ${params.DATABASENAME_183}" //本地
      }
    }
  }
}

