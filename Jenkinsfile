pipeline
{
agent any
tools
{
maven 'maven'
}
stages
{
stage('chekout')
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