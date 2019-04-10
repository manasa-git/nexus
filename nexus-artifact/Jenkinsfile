node {
    notify('started')
//     stage('checkout') {

  //       git 'https://github.com/manasa-git/jenkins.git'

    // }
  
    def project_path = "spring-boot-samples/spring-boot-sample-atmosphere"
    
    dir ('project_path') {

        stage('compile_test_package') {

        sh 'mvn clean package'

        }
        stage('git') {
            
        archiveArtifacts 'target/*.jar'
 
        }

    }

}
def notify(status){
    emailext (
      to: "anil.maharshi@gmail.com",
      subject: "${status}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
      body: """<p>${status}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
        <p>Check console output at <a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a></p>""",
    )
}






