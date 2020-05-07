
pipeline {    
agent any
stages  { 
stage('1') {
  steps {
        checkout([
          $class: 'GitSCM',
          branches: [[name: '*/master']],
          userRemoteConfigs: [[credentialsId: 'c181bd83-f1f4-49f2-8367-f95dee1a9571',
          url: 'https://github.com/PrasannaCo/mavenrepo.git']]
        ])
        }
       }

stage('build') {
  steps {
sh 'mvn package'
        }
       }

	stage('sonar') {
  steps {
withSonarQubeEnv('sonar')
{
sh "mvn sonar:sonar"
}
        }
       }

	
	                }

              }             
