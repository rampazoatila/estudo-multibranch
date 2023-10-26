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
            echo getGitBranchName()
            if(env.BRANCH_NAME == "homolog")
            {
                echo "Building $BRANCH_NAME"
            }else{ 
                echo "Tag $TAG_NAME"
            }
            
            
        }
    }
} 

