pipeline{
    agent{label 'UBUNTU_JDK82'}
    parameters { choice(name: 'MAVEN_GOAL', choices: ['package', 'install', 'clean'], description: 'MAVEN GOAL') }
    stages{
        stage('VCS'){
            steps{
                git url:'https://github.com/vinaykumar56-2023/GameofLife.git',
                branch: 'declarative'
            }
        }
        stage('package'){
            tools{
              jdk 'jdk_8_ubuntu'
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