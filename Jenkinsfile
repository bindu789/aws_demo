pipeline {
    agent any
    stages {
        stage('clone git repo') {
            steps {
               git branch: 'hima', credentialsId: 'fdcf4e88-c1ab-416a-b1da-a620c1e96c71', url: 'https://github.com/bindu789/teams.git'
            }
        }
        stage('build') {
            steps {
               sshPublisher(publishers: [sshPublisherDesc(configName: 'react_server', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''ls
pwd''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '.', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: true)])
            }
        }
    }
}