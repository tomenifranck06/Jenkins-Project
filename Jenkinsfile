pipeline {
    agent any

    stages {

        stage('Cloner le site HTML') {
            steps {
                git 'https://github.com/tomenifranck06/TON_DEPOT.git'
            }
        }

        stage('Déployer sur Nginx') {
            steps {
                sh """
                sudo rm -rf /var/www/html/mon-site/*
                sudo cp -r * /var/www/html/mon-site/
                sudo chown -R www-data:www-data /var/www/html/mon-site
                sudo systemctl reload nginx
                """
            }
        }
    }
}
