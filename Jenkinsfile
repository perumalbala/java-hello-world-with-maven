#!/usr/bin/env groovy
def appName= 'testing'
def major_version = 1.0 


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
    def build_number =  BUILD_NUMBER
    def appVersion = major_version + build_number
    sh 'mv "$WORKSPACE"/target/jb*.jar "$WORKSPACE"/target/"${appName}"."${appVersion}".jar'
    echo "The current application name is ${appName}.${appVersion}.jar"
    sh 'ls -la target/'
  }
}
