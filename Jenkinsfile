pipeline{
    agent{label 'UBUNTU_JDK82'}
    triggers { pollSCM('*/10 * * *') }
    parameters { choice(name: 'MAVEN_GOAL', choices: ['package', 'install', 'clean'], description: 'MAVEN GOAL') }
    stages{
        stage('VCS'){
            steps{
                git url:'https://github.com/vinaykumar56-2023/GameofLife.git',
                branch: 'declarative'
            }
        }
        stage('package'){
            steps{
                sh 'export PATH="/usr/lib/jvm/java-1.8.0-openjdk-amd64/bin:$PATH'
            }
            steps{
               sh "mvn ${params.MAVEN_GOAL}"
            }            
        }
        stage('post build'){
            steps{
               archiveArtifacts artifacts: '**/target/gameoflife.war', onlyIfSuccessful:true
            }            
        }
    }
}