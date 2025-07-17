pipeline {
    agent any 
    stages {
        stage('Build') {
      steps {
        // PowerShell のコンソール出力を UTF-8 に変える
        powershell '''
          [Console]::OutputEncoding = [System.Text.Encoding]::UTF8
          chcp 65001
          dotnet restore
          dotnet build --no-restore
        '''
      }
    }
        // stage('Test') { 
        //     steps {
        //         sh 'dotnet test --no-build --no-restore --collect "XPlat Code Coverage"'
        //     }
        //     post {
        //         always {
        //             recordCoverage(tools: [[parser: 'COBERTURA', pattern: '**/*.xml']], sourceDirectories: [[path: 'SimpleWebApi.Test/TestResults']])
        //         }
        //     }
        // }
        // stage('Deliver') { 
        //     steps {
        //         sh 'dotnet publish SimpleWebApi --no-restore -o published' 
        //     }
        //     post {
        //         success {
        //             archiveArtifacts 'published/*.*'
        //         }
        //     }
        // }
    }
}