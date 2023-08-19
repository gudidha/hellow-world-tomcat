node('tomcat') {
    stage('scm') {
	git 'https://github.com/gudidha/hellow-world-tomcat.git'
    }
    stage('BUILD') {
	  if env.branch == 'master'
	    sh 'mvn clean package'
	  else 
	    sh 'mvn clean package'
    }
	stage('test results and package') {
    archive 'target/*.war'
    } 
	stage('Restart'){
	sh '''tomactdown
    sleep 10s
    tomcatup'''
	}
}

