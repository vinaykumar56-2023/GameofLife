node('UBUNTU_JDK82')
{
    stage('version control')
    {
        git url:'https://github.com/vinaykumar56-2023/GameofLife.git'
        branch: 'scripted'
    }
    stage('build the code ')
    {
        sh 'export PATH="/usr/lib/jvm/java-1.8.0-openjdk-amd64/bin:$PATH" && mvn package'
    }
    stage('archive the artifacts')
    {
        archiveArtifacts artifacts: '**/target/gameoflife.war', followSymlinks: false
        
    }
    
}