properties([pipelineTriggers([pollSCM('')])])

node{  
    
    stage('Introduction'){
    echo 'Hello-- Welcome to Pipeline Demo'
  }
    
    stage('SCM Checkout'){
 git credentialsId: 'github', 
		    url: 'https://github.com/glamraj/my-apps',
			branch: "${params.gitBranch}"
  }

    stage('Maven Build'){ 
    tool name: 'M2', type: 'maven'
    sh label: '', script: 'mvn clean package'
  }
    
    stage('JUnit Publisher'){ 
    junit allowEmptyResults: true, testResults: '/var/lib/jenkins/workspace/pipeline-demo/target/surefire-reports/**.xml'
  }
    
}
