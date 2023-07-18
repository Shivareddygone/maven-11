@Library("mylibrary")_

node("built-in")
{
    stage('continuous download')
    {
        cicd.newgit("maven.git")
    }
    stage('continuous built')
    {
        cicd.newMaven()
    }
    stage('continuous deployment')
    {
        cicd.newdeploy("sharedlibrariespipeline","172.31.93.250","testapp")
    }
    stage('continuous testing')
    {
        cicd.newgit("FunctionalTesting")
        cicd.runselenium("sharedlibrariespipeline")
    }
    stage('continuous delivery')
    {
        cicd.newdeploy("sharedlibrariespipeline","172.31.94.96","prodapp")
    }
}
