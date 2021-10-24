node
  {
  stage('checkout')
    {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-tags', url: 'https://github.com/sriram-naresh/mutli-project.git']]])
    }
   stage("Build"){
       steps{
         sh """
           mvn clean
           mvn install
         """
      }
    }
  }

