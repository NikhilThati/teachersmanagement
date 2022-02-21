pipeline{
  agent {label 'main'}
  stages{
    stage('Cleaning WS'){
      steps{
        cleanWs()
      }
    }
    stage('repo pulling'){
      steps{
        git branch: 'main', url: 'https://github.com/NikhilThati/teachersmanagement.git'
        sh "ls"
      }
    }
    stage('Terraform code exucution'){
      steps{
        sh "aws lambda create-function --function-name my-function --runtime python3.9 --timeout 840 --zip-file fileb://my-function.zip --handler my-function.lambda_handler  --role arn:aws:iam::748834350686:role/demo-Role --region us-east-2"
      }
    }
    stage('Cleaning WS1'){
      steps{
        cleanWs()
      }
    }
  }
}
