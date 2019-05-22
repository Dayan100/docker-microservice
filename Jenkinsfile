node {
  stage('SCM Checkout') {
    git 'https://github.com/harishanumandla817/docker-microservice.git'
    stage('Compile-Package') {
      def mvnHome = tool name: 'Apache Maven 3.3.9', type: 'maven'
      '${mvnHome}/bin/mnv install'
    }
  }
}
