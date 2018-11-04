node {
	stage 'Build'
		

	stage 'Archive'
		archive 'ConsoleApp/bin/Release/**'

}

pipeline {
    agent { label 'DotNetFX' }
    stages {
        stage('Example') {
            steps {
                bat "\"${tool 'MSBuild'}\" TestNetFX.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
            }
        }
    }
}