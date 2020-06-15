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
chekout scm
}
}

stage('build')
{
steps
{
bat "mvn clean install"
}
}
}
}
