try {
   timeout(time: 20, unit: 'MINUTES') {
      node('nodejs') {
          stage('build') {
            openshiftBuild(buildConfig: 'http-base', showBuildLogs: 'true')
          }
          stage('deploy') {
            openshiftDeploy(deploymentConfig: 'http-base')
          }
        }
   }
} catch (err) {
   echo "in catch block"
   echo "Caught: ${err}"
   currentBuild.result = 'FAILURE'
   throw err
}         