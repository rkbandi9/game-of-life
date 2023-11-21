node('node1_jdk')
{
    stage('version control system')
         git url: 'https://github.com/rkbandi9/game-of-life.git',
             branch : 'scripted'

    stage('Build')
         sh 'export PATH="/usr/lib/jvm/java-1.8.0-openjdk-amd64/bin:$PATH" && mvn package'

    stage('archive the artifact')
         onlyIfSuccessful: yes,
         archiveArtifacts artifacts: '**/target/*.war'
    
    stage('show test result')
         junit testResults: '**/surefire-reports/TEST-*.xml',
         allowEmptyResults: yes
}

    
   
   
   