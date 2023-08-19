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
	stage('Deploy') { 
	deploy adapters: [tomcat9(credentialsId: '4e5f019d-1d13-43ea-b4d9-8fbee2c7ee88', path: '', url: 'http://13.58.82.20:8080')], contextPath: 'hello-world-maven', war: '**/*.war'
    }
	stage('Restart'){
	sh '''tomactdown
    sleep 10s
    tomcatup'''
	}
}
