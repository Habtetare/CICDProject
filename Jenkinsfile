pipeline{
agent any
stages {
	stage('Build Application') {
	steps {
	bat 'mvn clean install'
	}
	}
stage('Deploy CloudHubs'){
environment{
ANYPOINT_CREDENTIALS = credentials('83d56fc02111486b8509000386bf996d')
}
steps {
echo 'Deploying mule project due to the latest code commit…'
echo 'Deploying to the configured environment….'
bat 'mvn clean deploy -DmuleDeploy -Dmule.app.name=CICDProject -Dusername=Tare65 -Dpassword=Tsuper12356'
}
}
}
}