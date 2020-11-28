pipeline { 
  agent any 
  node {
    env.NODEJS_HOME = "${tool 'Node 5.8'}"
    env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
    sh 'npm --version'
  }

  tools {nodejs "node"} 
  stages { 
    stage('Cloning Git') { 
      steps { 
        git 'https://github.com/chriswolske/node-todo-frontend' 
      } 
    } 
    stage('Install dependencies') { 
      steps { 
	sh 'npm install' 
      } 
    } 
    stage('Test') { 
      steps { 
	sh 'npm test' 
      } 
    } 
  } 
}
