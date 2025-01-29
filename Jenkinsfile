job('gitlab-connection') {
    description('Freestyle jobs run on GitLab push')

    triggers {
        gitlabPush {
            buildOnPushEvents(true)    // プッシュ時にジョブを実行
            buildOnMergeRequestEvents(true)  // マージリクエスト時にも実行（false にすれば無効化）
            enableCiSkip(true)  // [ci skip] のコミットメッセージを尊重
            setBuildDescription(true)  // GitLabの情報をジョブの説明に設定
            addNoteOnMergeRequest(false)  // マージリクエストにコメントを追加しない
            addCiMessage(false)  // GitLabのCIステータスを更新しない
        }
    }

    scm {
        git {
            remote {
                url('https://gitlab.com/example/repo.git')
                credentials('gitlab-credentials-id')  // Jenkinsに登録したGitLabの認証情報ID
            }
            branch('*/main')
        }
    }

    steps {
        shell('echo "Building the project..."')
        shell('echo "Running tests..."')
        shell('echo "Deploying the application..."')
    }

    publishers {
        archiveArtifacts('**/target/*.jar')  // 成果物を保存（適宜変更）
    }
}
