#!/usr/bin/env groovy
def appName= 'testing'
def major_version = 1.0 
def build_number = sh "echo $BUILD_NUMBER".split()
def appVersion = major_version + build_number

node{

stage('cloning repo'){
  checkout scm
}

stage('Testing')
{
sh 'mvn clean test'
}

stage('Build the code')
{
sh 'mvn clean install'

}

stage('saving artifacts')
  {
    sh 'sh /var/lib/jenkins/workspace/test11111/target/jb*.jar /var/lib/jenkins/workspace/test11111/target/${appName}.${appVersion}.jar'
    echo "The current application name is ${appName}.${appVersion}.jar"
    sh 'ls -la target/'
  }
}
