#!/usr/bin/env groovy
import hudson.model.*

node('master') {


//library ('utils@master') _

def MAJOR_VERSION = "1"
def ARTIFACT_VERSION = "${MAJOR_VERSION}.${BUILD_NUMBER}"
def STACK_NAME = "intl-latam-poliza-backend-jenks"
def STACK_NAME_API = "intl-latam-poliza-apigateway-jenks"
//node('linux'){


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


}


//}

/*

deployToDev{
  stage('Git Checkout'){
    checkout scm

sh """	
				
                aws s3 cp CODE/* s3://intl-latam-ec-poliza-bucket/ --recursive
                ls -latr
            """

  }

  stage('Upload to Artifactory'){
      //CFT and params files are artifacts for infrastructure deploys
      def artifacts = ['intl-latam-poliza-resources-params-dev.json', 'intl-latam-poliza-apigateway.json']
      artifactoryUploadFiles files:artifacts,version:ARTIFACT_VERSION
  }

  stage('Dev Deploy'){
      cfnDeploy(file:'intl-latam-poliza-cloudformation-resources.json', stackName:"${STACK_NAME}", cftParamsFile:'intl-latam-poliza-resources-params-dev.json')
     
      cfnUpdate(stack:"${STACK_NAME_API}", params:["urlHostApi=api-dev.liberty.ec", "stageDeploy=developer"
      , "prefixName=intl-latam-ec","roleId=arn:aws:iam::318809572658:role/intl-latam-ec-role-dev", "projectName=poliza",
      "stackNameSecure=intl-latam-ec-secure-b2b-dev","stackName=intl-latam-poliza-backend-jenks","basePath=poliza",
      "domainFrontEnd=intermediarios-dev.liberty.ec", "protocol=https://"],
            url:'https://s3.amazonaws.com/intl-latam-ec-poliza-bucket/intl-latam-poliza-apigateway.json')
    }
  }
}

*/
