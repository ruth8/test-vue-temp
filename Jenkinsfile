pipeline {
    agent any

    

    stages {
        stage('Checkout') {
            steps {
                echo "拉取代码"
                git branch: 'main', url: 'https://github.com/ruth8/test-vue-temp.git'
            }
        }

        stage('Install & Build') {
            steps {
                sh '''
                docker run --rm \
                -v "$WORKSPACE:/app" \
                -w /app \
                node:20-alpine \
                sh -c 'npm ci && npm run build'
                '''
            }
        }

        stage('Archive') {
            steps {
                echo "归档构建产物"
                archiveArtifacts artifacts: 'dist/**', fingerprint: true
            }
        }

        stage('Deploy') {
            steps {
                echo "部署前端到服务器"
                // 实际部署：在 Jenkins 中配置 DEPLOY_* 环境变量及 SSH 凭据后，取消下面注释
                // withCredentials([sshUserPrivateKey(credentialsId: 'deploy-ssh-key', keyFileVariable: 'SSH_KEY')]) {
                //     sh 'scp -i "$SSH_KEY" -o StrictHostKeyChecking=no -r dist/* ${DEPLOY_USER}@${DEPLOY_HOST}:${DEPLOY_PATH}'
                // }
                sh 'echo "部署完成，dist 已归档（启用 scp 需配置凭据并取消注释）"'
            }
        }
    }

    post {
        success {
            echo "Jenkins 构建完成 ✅"
        }
        failure {
            echo "Jenkins 构建失败 ❌"
        }
    }
}