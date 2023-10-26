def label = "teste"
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
            if(env.BRANCH_NAME == "homolog")
            {
                echo "Building $BRANCH_NAME"
            }else{ 
                echo "Tag $TAG_NAME"
            }
            
            
        }
    }
} 

