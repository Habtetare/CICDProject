pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Deploy CloudHubs') {
            environment {
                ANYPOINT_CREDENTIALS = credentials('83d56fc02111486b8509000386bf996d')
            }
            steps {
                echo 'Deploying Mule project due to the latest code commit…'
                echo 'Deploying to the configured environment….'

                // Make sure the whole command is inside quotes
                bat '''
                    mvn clean deploy -DmuleDeploy ^
                    -Dmule.app.name=CICDProject ^
                    -Dusername=Tare65 ^
                    -Dpassword=Tsuper12356 ^
                    -Dtarget=Sandbox
                '''
            }
        }
    }
}
