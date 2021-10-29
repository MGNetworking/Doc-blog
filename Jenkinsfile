node {
    
    
    def ID_CREDENTIAL = 'a995d9c5-a16f-4f87-8c33-7b40e16f9f20'
    def SSH_URL_GITHUB = 'git@github.com:MGNetworking/ghoverblog_Documentation-.git'
    def Branch = 'main'
    

    stage('Clone du projet') {

        echo '***************************************'
        echo '          Clone du projet'
        echo '***************************************'
            
        // get depot with credentials
        git branch: Branch , credentialsId: ID_CREDENTIAL , url: SSH_URL_GITHUB
                
    }

    stage('Récupération de l\'environement Python') {

        echo '***************************************'
        echo 'Récupération de l\'environement Python'
        echo '***************************************'
                    
        // recupération de l'environement Python a partir du fichier requirements.txt
        sh '''  pip install -r requirements.txt '''
                
    }

    // Phase de gestion de compilation de la documentation 
    stage('Build de la documentation') {

        echo '************************************'
        echo '      Build de la documentation'
        echo '************************************'

        // création de l'environement
        sh "sudo virtualenv env"
                    
        // placer le terminal dans l'environement
        sh ". env/bin/activate"

        // Importé et installer les dépendances du projet dans l'environement Python 
        sh "pip install -r requirements.txt"

        // Compilation du projet dans le repertoire de jenkins
        sh "make html"
    }

    // supression de la version précedante 
    stage(' Suppression de l\'ancienne version ') {

        echo '************************************'
        echo ' Suppression de l\'ancienne version '
        echo '************************************'

        try{
                            
            sh ''' rm -r /home/prod/doc-ghoverblog/* '''
            

        }catch (errors) {
            
            echo '********************************'
            echo 'Fichier source non supprimer !!!'
            echo '********************************'

            currentBuild.result = 'FAILED'

        }finally{

            if (currentBuild.result != 'FAILED'){
            echo '************************************'
            echo 'Etape suppression de fichier finis '
            echo '************************************'
            }                  
        }
                
    }

    stage('Copie du build vers répertoir d\'accueil' ) {
         
        echo '******************************************'
        echo 'Copie du build vers répertoir d\'accueil'
        echo '******************************************'

        //  déplacement du build vers le fichier html
        sh "cp -r /var/lib/jenkins/workspace/Documentation-ghoverblog/_build/html/* /home/prod/doc-ghoverblog/"

        cleanWs()
       
    }
}