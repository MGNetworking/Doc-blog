node {

    stage('Clone du projet ') {
        // get depot with credentials
        git branch: 'main', credentialsId: 'a995d9c5-a16f-4f87-8c33-7b40e16f9f20' , url: 'git@github.com:MGNetworking/ghoverblog_Documentation-.git'
    }
    
    stage('**************************************** \n Récupération de l\'environement Python \n ****************************************') {
        // recupération de l'environement Python a partir du fichier requirements.txt
        sh '''  pip install -r requirements.txt '''
     }


    // Phase de gestion de compilation de la documentation 
    stage('**************************************** \n  Build to documentation \n **************************************** ') {

        // création de l'environement
        sh ''' python3 -m venv env '''

        // placer le terminal dans l'environement
        sh ''' source ./env/bin/activate '''

        // Importé et installer les dépendances du projet dans l'environement Python 
        sh ''' pip install -r requirements.txt '''

        // Compilation du projet dans le repertoire de jenkins
        sh '''  make html '''
     }

    stage('**************************************** \n Suppression de l\'ancienne version \n **************************************** ') {
        // supression de la version précedante 
        sh ''' rm -r /home/prod/doc-ghoverblog/* '''
    }

    stage('**************************************** \n Déplacement du build vers répertoir d\'accueil \n **************************************** ' ) {
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