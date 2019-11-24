#!/usr/bin/env groovy
def appName= 'testing'
def major_version = 1.0 
def build_number = ${BUILD_NUMBER}
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
sh 'ls -la'
}

stage('saving artifacts')
  {
    sh 'sh $WORKSPACE/target/jb*.jar $WORKSPACE/target/${appName}.${appVersion}'
    sh 'ls -la'
  }
}
