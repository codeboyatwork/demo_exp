node('') {
	    // reference to maven
	    // ** NOTE: This 'maven-3.5.2' Maven tool must be configured in the Jenkins Global Configuration.   
	    def mvnHome = tool 'maven'

	    
	    stage('Clone Repo') { // for display purposes
	      // Get some code from a GitHub repository
	      git 'https://github.com/codeboyatwork/demo_exp.git'
	      // Get the Maven tool.
	      // ** NOTE: This 'maven-3.5.2' Maven tool must be configured
	      // **       in the global configuration.           
	      mvnHome = tool 'maven'
	    } 
	    stage('Compile') {
	      // build project via maven
	      configFileProvider([configFile(fileId: '877e4e12-0ffb-40b9-9113-7b5378e29634', targetLocation: 'maven-settings', variable: 'MAVEN_SETTINGS')]) {
	      sh "'${mvnHome}/bin/mvn' -s $MAVEN_SETTINGS clean compile"
		}

	    }
	    stage('Build Project') {
	      // build project via maven
	      configFileProvider([configFile(fileId: '877e4e12-0ffb-40b9-9113-7b5378e29634', targetLocation: 'maven-settings', variable: 'MAVEN_SETTINGS')]) {
	      sh "'${mvnHome}/bin/mvn' -s $MAVEN_SETTINGS clean install"
		}

	    }
}
