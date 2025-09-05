// pipeline {
//     agent any
//     parameters {
//         choice(name: 'BUILD_TYPE', choices: ['development', 'production'], description: 'Select the build type')
//     }
//     stages {
//         stage('Hello') {
//             steps {
//                 echo 'Hello World'
//             }
//         }
//     }
// }



pipeline {
    agent any
    
    parameters {
        // Git SHA 輸入框
        string(name: 'GIT_SHA', defaultValue: '', description: 'Enter the Git SHA')

        // 部門選擇下拉選單
        choice(name: 'DEPARTMENT', choices: ['SVD', 'FW', 'SW'], description: 'Select the department')

        // Build 類型選擇下拉選單
        choice(name: 'BUILD_TYPE', choices: ['CI/CD', 'Normal test', 'Validation'], description: 'Select the build type')
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // 獲取參數值
                    def gitSha = params.GIT_SHA
                    def department = params.DEPARTMENT
                    def buildType = params.BUILD_TYPE

                    // 輸出參數值
                    echo "Git SHA: ${gitSha}"
                    echo "Department: ${department}"
                    echo "Build Type: ${buildType}"

                    // 根據不同的參數執行不同邏輯
                    if (buildType == 'CI/CD') {
                        echo "Running CI/CD pipeline for ${department}..."
                    } else if (buildType == 'Normal test') {
                        echo "Running Normal test for ${department}..."
                    } else if (buildType == 'Validation') {
                        echo "Running Validation for ${department}..."
                    }
                }
            }
        }
    }
}
