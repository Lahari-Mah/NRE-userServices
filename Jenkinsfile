pipeline
{
  agent any
  stages{
    stage('Build Application'){
      steps{
    		sh 'mvn clean install -DskipTests'
    	}
    }
    
    stage('Deploy Application to MuleSoft CloudHub'){
     steps{
    		sh 'mvn package deploy -DmuleDeploy -DskipTests'
    	}
    }
    
    stage('Perform Regression Testing'){
      steps{
    		sh 'newman run /Users/rm/Desktop/NjcLabs/newman/getUser.postman_collection.json -r htmlextra --reporter-htmlextra-export /Users/rm/Desktop/NjcLabs/newman'
    	}
    }
  }
}