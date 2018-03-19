node {

    stage ('Checking out Git Repo') {
            checkout([$class: 'GitSCM', branches: [[name: '${sha1}']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '47892ef6-6b59-43fc-8ee9-5678ff13ed34', name: 'origin', refspec: '+refs/pull/*:refs/remotes/origin/pr/*', url: 'https://github.com/agnnn/pet-solidity.git']]])
    }
    
    stage ('Starting Ganache test Blockchain'){
            build job: 'Ganache test block chain', wait: false
    }
    
    stage ('Truffle testing using development network') {
        sh '''sleep 20
            truffle test'''
    }
}
