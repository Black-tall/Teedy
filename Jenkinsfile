pipeline {
    agent any
    
    stages {
        stage('Maven 构建') {
            steps {
                sh 'mvn clean compile'
            }
        }
        
        stage('PMD 代码检查') {
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        
        stage('运行测试') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('生成测试报告') {
            steps {
                sh 'mvn surefire-report:report'
            }
        }
        
        stage('生成 JavaDoc') {
            steps {
                sh 'mvn javadoc:javadoc'
            }
        }
        
        stage('打包 JAR') {
            steps {
                sh 'mvn package -Dmaven.test.skip=true'
            }
        }
    }
}
