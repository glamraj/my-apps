node{  
    
    stage('Introduction'){
    echo 'Hello-- Welcome to Pipeline Demo'
  }
    
    stage('SCM Checkout'){
    git 'https://github.com/javahometech/my-app'
  }

    stage('Maven Build'){ 
    tool name: 'M2', type: 'maven'
    sh label: '', script: 'mvn clean package'
  }
    
    stage('JUnit Publisher'){ 
    junit allowEmptyResults: true, testResults: 'pipeline-demo/target/surefire-reports/*.xml'
  }
    
}
