timestamps {

node ('zip') { 

	stage ('RedTardisRP - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'radialbog9ci-gh', url: 'https://github.com/TheJoeCoder/RedTardisRP']]]) 
	}
	stage ('RedTardisRP - Build') {
 			// Shell build step
sh """ 
zip -r redtardis.zip *
 """
		archiveArtifacts allowEmptyArchive: false, artifacts: 'redtardis.zip', caseSensitive: true, defaultExcludes: true, fingerprint: false, onlyIfSuccessful: false 
	}
}
}