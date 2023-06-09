node('built-in') {
    stage('contiNuousDownload')
    {
       git 'https://github.com/mankinimbom/maven.git'
    } 
    stage('contiNuousBuild')
    {
      sh 'mvn clean install'
    }
    stage('contiNuousTesting')
    {
       git 'https://github.com/mankinimbom/testingproject.git'
       sh 'java -jar  /var/lib/jenkins/workspace/peter_script/testing.jar'
    }
    stage('contiNuousDeployment')
    {
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://4.227.254.138:8083')], contextPath: 'Adrenaline', war: '**/*.war'
    }
    
}
