library ('utils@master') _

def MAJOR_VERSION = "1"
def ARTIFACT_VERSION = "${MAJOR_VERSION}.${BUILD_NUMBER}"
def STACK_NAME = "intl-latam-poliza-backend-jenks"
def STACK_NAME_API = "intl-latam-poliza-apigateway-jenks"
node('linux'){

stage('Git Checkout'){
    checkout scm
  }

stage('Validate parameters') {
        sh """
		ls -ltr
		 cd intermediarios 
		npm install		
        """
}


deployToDev{
  stage('Git Checkout'){
    checkout scm

sh """	
      cd intermediarios
      npm install
   """
  }
 }
 }




