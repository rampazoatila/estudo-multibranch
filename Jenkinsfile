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
        stage('Deploy')
        {
            echo "Deploy"
        }
        stage('Release')
        {

            if(getGitBranchName() == "homolog")
            {
                echo "Building ${getGitBranchName()}"
            }else{ 
                echo "TAG ${getGitBranchName()}" 
            }
            
            
        }
    }
} 

