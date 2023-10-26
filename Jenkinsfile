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
                echo "Building $BRANCH_NAME"
                echo "Building $TAG_NAME"
        }
    }
} 
