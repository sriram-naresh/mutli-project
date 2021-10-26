node
  {
  stage('checkout')
    {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-tags', url: 'https://github.com/sriram-naresh/mutli-project.git']]])
    }
  stage('deploy')
    {
    echo 'branch name ' + env.BRANCH_NAME
    
    if (env.BRANCH_NAME.startsWith("test2"))
      {
      echo "Deploying to Dev environment after build"
      }
      
    else if (env.BRANCH_NAME.startsWith("dev"))
      {
      echo "Deploying to Stage after build and Dev Deployment"
      }
      
    else if (env.BRANCH_NAME.startsWith("master"))
      {
      echo "Deploying to PROD environment"
      }
      
    sh """chmod +x HelloWorld.sh 
    ./HelloWorld.sh"""
 
    }
}
