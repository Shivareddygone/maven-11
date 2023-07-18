@Library("mylibrary")_

node("built-in")
{
    stage('continuous download_Loans')
    {
        cicd.newgit("maven.git")
    }
    stage('continuous built_Loans')
    {
        cicd.newMaven()
    }
}
