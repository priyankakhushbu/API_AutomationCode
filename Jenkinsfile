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
	bat "mvn clean install -DskipTests"
	}
}

stage('Docker Build Image')
{
steps
	{
	script{
		docker.build("test-image", "./")
		}
	}
}

}
}
