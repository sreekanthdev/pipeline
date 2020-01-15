node('master') {
    stage('ContinuousDownload') {
        git 'https://github.com/selenium-saikrishna/maven.git'
}
    stage('ContinuousBuild') {
    sh label: '', script: 'mvn package'
}
stage('ContinuousDeployment') 
{
	sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ss/webapp/target/webapp.war ubuntu@172.31.90.28:/var/lib/tomcat8/webapps/qaenv1.war'
}
    
stage('ContinuousTesting') 
{
    
	git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'

}
    
stage('ContinuousDelivery') 
{
    
	sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ss/webapp/target/webapp.war ubuntu@172.31.94.126:/var/lib/tomcat8/webapps/prodenv1.war'
}
}
