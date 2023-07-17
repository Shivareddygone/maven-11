pipeline
{
    agent any
    stages
    {
        stage('continuous download')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'    
            }
        }
        stage('continuous buit')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('contiuous deployment')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: 'b75d8f56-a8ac-495e-887c-5036623640b4', path: '', url: 'http://172.31.87.185:8080')], contextPath: 'testapp', war: '**/*.war'
            }
        }
        stage('continuous testing')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
              sh 'java -jar /var/lib/jenkins/workspace/scriptedpipeline1/testing.jar'
            }
        }
        stage('continuous delivery')
        {
            steps
            {
              
             deploy adapters: [tomcat9(credentialsId: 'b75d8f56-a8ac-495e-887c-5036623640b4', path: '', url: 'http://172.31.94.66:8080')], contextPath: 'prodapp', war: '**/*.war'
            }
        }
    }
}
