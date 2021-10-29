node {

    environment {
        ID_CREDENTIAL = 'a995d9c5-a16f-4f87-8c33-7b40e16f9f20'
        SSH_URL_GITHUB = 'git@github.com:MGNetworking/ghoverblog_Documentation-.git'
        Branch = 'main'
    }

    stage('Clone du projet') {
        // get depot with credentials
        git branch: 'main' , credentialsId: 'a995d9c5-a16f-4f87-8c33-7b40e16f9f20' , url: 'git@github.com:MGNetworking/ghoverblog_Documentation-.git'
    }
    
    stage('Récupération de l\'environement Python ') {
        // recupération de l'environement Python a partir du fichier requirements.txt
        sh '''  pip install -r requirements.txt '''
     }


    // Phase de gestion de compilation de la documentation 
    stage('Build de la documentation') {

                // création de l'environement
                sh '''sudo virtualenv env '''
             

            
                // placer le terminal dans l'environement
                sh ''' . env/bin/activate '''
            

           
                // Importé et installer les dépendances du projet dans l'environement Python 
                sh ''' pip install -r requirements.txt '''
           

            
                // Compilation du projet dans le repertoire de jenkins
                sh '''  make html '''
        
     }

    // supression de la version précedante 
    stage(' Suppression de l\'ancienne version ') {

        try{
            
            sh ''' rm -r /home/prod/doc-ghoverblog/* '''
            currentBuild.result = 'FAILED'

        }catch (errors) {
            echo 'Fichier source no supprimer !'
        }finally{
            if (currentBuild.result != 'FAILED'){
                echo 'Suppression de fichier réussi !'
            }
        }

    }

    stage('Déplacement du build vers répertoir d\'accueil' ) {
        //  déplacement du build vers le fichier html
        sh '''cp -r /var/lib/jenkins/workspace/Documentation-ghoverblog/_build/html/* /home/prod/doc-ghoverblog/ '''
    }


    post {

        // Déactivatation de l'environement du terminal 
        sh ''' deactivate '''

        // suppression des élements contenu dans le repertoire temporaire
        always {
            cleanWs()
        }
  }
}