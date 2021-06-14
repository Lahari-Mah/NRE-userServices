pipeline
{
  agent any
  stages{
    stage('Build Application'){
      steps{
    		sh 'mvn clean install -DskipTests'
    	}
    }
    
    stage('Munit Testing'){
     steps{
    		sh 'mvn test'
    	}
    }
    
    stage('Deploy Application to MuleSoft CloudHub'){
     steps{
    		sh 'mvn package deploy -DmuleDeploy -DskipTests'
    	}
    }
    
    stage('Perform Regression Testing'){
      steps{
    		sh 'newman run /Users/rm/Desktop/NjcLabs/newman/getUserServices.postman_collection.json'
    	 }
    }
  }
}