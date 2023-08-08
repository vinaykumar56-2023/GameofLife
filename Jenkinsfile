pipeline{
    agent{label 'UBUNTU_JDK82'}
    stages{
        stage('VCS'){
            steps{
                git url:'https://github.com/vinaykumar56-2023/GameofLife.git',
                branch: 'declarative'
            }
        }
        stage('package'){
            steps{
               sh 'export PATH="/usr/lib/jvm/java-1.8.0-openjdk-amd64/bin:$PATH" && mvn package'
            }            
        }
        stage('post build'){
            steps{
               archiveArtifacts artifacts: '**/target/gameoflife.war', onlyIfSuccessful:true
            }            
        }
    }
}