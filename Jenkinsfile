pipeline{
    agent{label 'UBUNTU_JDK82'}
    stages{
        stage('VCS'){
            steps{
                git 'https://github.com/vinaykumar56-2023/GameofLife.git',
                branch: 'declarative'
            }
        }
        stage('package'){
            steps{
               sh 'mvn package'
            }            
        }
        stage('post build'){
            steps{
               archiveArtifacts artifacts: '**/target/gameoflife.war', followSymlinks: false
            }            
        }
    }
}