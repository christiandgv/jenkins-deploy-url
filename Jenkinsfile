library ('utils@master') _

def MAJOR_VERSION = "1"
def ARTIFACT_VERSION = "${MAJOR_VERSION}.${BUILD_NUMBER}"
//def  = "intl-latam-poliza-backend-jenks"
//def STACK_NAME_API = "intl-latam-poliza-apigateway-jenks"
node('linux'){

stage('Git Checkout'){
    checkout scm
  }

stage('Validate parameters') {
  withAWS(credentials:getAWSCredentialID(environment:"${env.APPENV}"), region:'us-east-1') {
        
        
        
        sh """
    if aws s3 ls "s3://$BUCKET_NAME" 2>&1 | grep -q 'NoSuchBucket'
          then
          echo "bucket $BUCKET_NAME exist"
          else 
          aws s3 mb s3://$BUCKET_NAME
    fi
		ls -ltr
		 cd intermediarios 
		npm install	
    aws s3 cp ./dist s3://$BUCKET_NAME --acl public-read --recursive
        """

deployToDev{
  stage('Git Checkout'){
    checkout scm

sh """	
      
      npm install
   """
  }
 }
}
}
 }




