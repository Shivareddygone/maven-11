pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                git 'https://github.com/Shivareddygone/maven-11.git'
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment')
        {
            steps
            {
               deploy adapters: [tomcat9(credentialsId: 'bfb67f1d-2f4e-430c-bb8d-30584116bd00', path: '', url: 'http://172.31.51.212:9090')], contextPath: 'test1', war: '**/*.war'
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline1/testing.jar'
            }
        }
       
    }
    

