def label = "teste"

def getGitBranchName() {


   def branchName = scm.branches[0].name


   branchName = branchName.replace('/','-').toLowerCase()


   return branchName


}

podTemplate(
    label: label) {
    node(label) {
        stage('Checkout Project') {
            checkout scm
        }
         stage('Sonarqube Scanner') {
            if(getGitBranchName() == "homolog" || getGitBranchName() == "main")
            {
                container('sonar-scanner') {
                    withSonarQubeEnv('SonarQube FS') {
                        sh "sonar-scanner -Dsonar.login=${SONAR_AUTH_TOKEN} -Dsonar.projectBaseDir=. -Dsonar.projectKey=adtech-backoffice  -Dsonar.projectName=adtech-backoffice -Dsonar.exclusions=app/Console/Kernel.php,app/Providers/BroadcastServiceProvider.php,bootstrap/*,public/index.php -Dsonar.language=php -Dsonar.host.url=https://sonarqube.fsvas.com"
                    }   
                }
            }
            
        }
        stage('Release')
        {
            if(getGitBranchName() == "homolog")
            {
                echo "Building ${getGitBranchName()}"
            }
            else if(getGitBranchName() == "main"){
            }
            else{ 
               stage('Get Approval'){
                    input "Vamos nessa!"
               }
               stage('Deploy'){
                echo "Subindo para producao ${getGitBranchName()}"
               }
            }
            
            
        }
    }
} 

