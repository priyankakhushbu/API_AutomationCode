pipeline
{
agent any
tools
{
maven 'maven'
}
stages
{
stage('checkout')
{
steps
{
checkout scm
}
}

stage('build')
{
steps
	{
	bat "mvn clean install"
	}
}

stage('sonar analysis')
{
steps
{
echo "Sonar"
withSonarQubeEnv("local sonar")
	{
	bat "mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar"
	}
}
}
stage('Docker Build Image')
{
steps
	{
	script{
	echo $BUILD_NUMBER	
	docker.build registry + ":$BUILD_NUMBER"
	}
	}
}

}
}
