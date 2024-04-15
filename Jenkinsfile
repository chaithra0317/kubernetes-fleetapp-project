pipeline {
	agent { label 'k8s' }
	environment {
		helmchartname="fleethelm"
		releasename="helmchart1"
  }

	stages {
    
		stage ( 'checkout' ) {
			steps {
				checkout scmGit(branches: [[name: '*/helm']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/chaithra0317/kubernetes-fleetapp-project.git']])
		    }
		}
    
		stage ( 'deploying to k8s' ) {
			steps {
				sh "helm upgrade --install $releasename /home/ubuntu/helm/$helmchartname "
			}
		}
	}
}
