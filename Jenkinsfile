node('master') 
{
    stage('ContinuousDownload_loans') 
    {
        git 'https://github.com/selenium-saikrishna/maven.git'
    }
    stage('ContinuousBuild_loans')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment_loans')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.23.186:/var/lib/tomcat8/webapps/qaenv.war'
    }
    stage('ContinuousTesting_loans')
    {
        git 'https://github.com/selenium-saikrishna/TestingNew.git'
        sh label: '', script: 'echo "Testing Passed"'
    }
    
}
