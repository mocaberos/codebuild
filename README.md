# CodeBuild動作確認用プロジェクト

[![Build Status](https://codebuild.ap-northeast-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiL2JucnF5TzV6ZmJxditxSkdtT2RFbERYRjRUdHpDTmRFWFQxQXVYK0F3Z2N5RnhId3IyVitFamNMZzZWNlRpZGlaRjVwNDJFSkcvL01HL09Iak4vUi9ZPSIsIml2UGFyYW1ldGVyU3BlYyI6IkpHMGFvNTByQVVHQ1RnQkEiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master)](https://ap-northeast-1.console.aws.amazon.com/codesuite/codebuild/projects/codebuild)

### AWS CodeBuildで状況に応じて処理を分けるため、いろんな場合の環境変数を細かく調査した
https://qiita.com/mocaberos/items/ebd77d5b8b0952e8bdf9
### 調査方法
buildspec.ymlでCodeBuildのデフォルトの環境変数がいろんな場面のどのような値になるかを調べるため、
CodeBuildを連携させたgithubリポジトリで様々な操作を行い、結果を記録しました。

## masterブランチに直接pushした場合
```text
AWS_DEFAULT_REGION:                 ap-northeast-1
AWS_REGION:                         ap-northeast-1
CODEBUILD_BATCH_BUILD_IDENTIFIER:   
CODEBUILD_BUILD_ARN:                arn:aws:codebuild:ap-northeast-1:085041388644:build/codebuild:ed00ef43-f18b-4653-9778-835e910ab2c3
CODEBUILD_BUILD_ID:                 codebuild:ed00ef43-f18b-4653-9778-835e910ab2c3
CODEBUILD_BUILD_IMAGE:              aws/codebuild/standard:5.0
CODEBUILD_BUILD_NUMBER:             1
CODEBUILD_BUILD_SUCCEEDING:         1
CODEBUILD_INITIATOR:                GitHub-Hookshot/1c6af21
CODEBUILD_KMS_KEY_ID:               arn:aws:kms:ap-northeast-1:085041388644:alias/aws/s3
CODEBUILD_LOG_PATH:                 ed00ef43-f18b-4653-9778-835e910ab2c3
CODEBUILD_PUBLIC_BUILD_URL:         
CODEBUILD_RESOLVED_SOURCE_VERSION:  6e0de7938dda5363e2192fe2a2ec39987a3573b0
CODEBUILD_SOURCE_REPO_URL:          https://github.com/mocaberos/codebuild.git
CODEBUILD_SOURCE_VERSION:           6e0de7938dda5363e2192fe2a2ec39987a3573b0
CODEBUILD_SRC_DIR:                  /codebuild/output/src253338704/src/github.com/mocaberos/codebuild
CODEBUILD_START_TIME:               1633069563930
CODEBUILD_WEBHOOK_ACTOR_ACCOUNT_ID: 88621008
CODEBUILD_WEBHOOK_BASE_REF:         
CODEBUILD_WEBHOOK_EVENT:            PUSH
CODEBUILD_WEBHOOK_MERGE_COMMIT:     
CODEBUILD_WEBHOOK_PREV_COMMIT:      ef92d61ca5d9d843a87a4022f99925d2e211a2f4
CODEBUILD_WEBHOOK_HEAD_REF:         refs/heads/master
CODEBUILD_WEBHOOK_TRIGGER:          branch/master
HOME:                               /root
```

## testブランチに直接pushした場合
```text
AWS_DEFAULT_REGION:                 ap-northeast-1
AWS_REGION:                         ap-northeast-1
CODEBUILD_BATCH_BUILD_IDENTIFIER:   
CODEBUILD_BUILD_ARN:                arn:aws:codebuild:ap-northeast-1:085041388644:build/codebuild:2bf185df-1108-4222-ac0e-64b3bd6f6e4d
CODEBUILD_BUILD_ID:                 codebuild:2bf185df-1108-4222-ac0e-64b3bd6f6e4d
CODEBUILD_BUILD_IMAGE:              aws/codebuild/standard:5.0
CODEBUILD_BUILD_NUMBER:             6
CODEBUILD_BUILD_SUCCEEDING:         1
CODEBUILD_INITIATOR:                GitHub-Hookshot/1c6af21
CODEBUILD_KMS_KEY_ID:               arn:aws:kms:ap-northeast-1:085041388644:alias/aws/s3
CODEBUILD_LOG_PATH:                 2bf185df-1108-4222-ac0e-64b3bd6f6e4d
CODEBUILD_PUBLIC_BUILD_URL:         https://ap-northeast-1.codebuild.aws.amazon.com/project/eyJlbmNyeXB0ZWREYXRhIjoiSVlBb0dpNlEyYVBOZEhRTjJtazFDYTFYZVZualpXeS96R3FrODM1T1JtQXF5Z0l0UWFKV2pZMjA0UnlUTW44cm9WbWQxOEE2dStBdEsxQWtpL1FZcVVRQkl1SVlMQitjR1AvVFI3Zjh1UT09IiwiaXZQYXJhbWV0ZXJTcGVjIjoiMU1EWmVYZHVCaTI0dExPMyIsIm1hdGVyaWFsU2V0U2VyaWFsIjoxfQ%3D%3D/build/2bf185df-1108-4222-ac0e-64b3bd6f6e4d
CODEBUILD_RESOLVED_SOURCE_VERSION:  19a4e968f4092fed2f171d8b8d68012823c57a2d
CODEBUILD_SOURCE_REPO_URL:          https://github.com/mocaberos/codebuild.git
CODEBUILD_SOURCE_VERSION:           19a4e968f4092fed2f171d8b8d68012823c57a2d
CODEBUILD_SRC_DIR:                  /codebuild/output/src004618187/src/github.com/mocaberos/codebuild
CODEBUILD_START_TIME:               1633092549136
CODEBUILD_WEBHOOK_ACTOR_ACCOUNT_ID: 88621008
CODEBUILD_WEBHOOK_BASE_REF:         
CODEBUILD_WEBHOOK_EVENT:            PUSH
CODEBUILD_WEBHOOK_MERGE_COMMIT:     
CODEBUILD_WEBHOOK_PREV_COMMIT:      0000000000000000000000000000000000000000
CODEBUILD_WEBHOOK_HEAD_REF:         refs/heads/test
CODEBUILD_WEBHOOK_TRIGGER:          branch/test
HOME:                               /root
```

## masterブランチからmasterブランチにPRを出した場合
```text
AWS_DEFAULT_REGION:                 ap-northeast-1
AWS_REGION:                         ap-northeast-1
CODEBUILD_BATCH_BUILD_IDENTIFIER:   
CODEBUILD_BUILD_ARN:                arn:aws:codebuild:ap-northeast-1:085041388644:build/codebuild:30ab0252-9d5b-4cf8-96a7-4c38b22d6df0
CODEBUILD_BUILD_ID:                 codebuild:30ab0252-9d5b-4cf8-96a7-4c38b22d6df0
CODEBUILD_BUILD_IMAGE:              aws/codebuild/standard:5.0
CODEBUILD_BUILD_NUMBER:             3
CODEBUILD_BUILD_SUCCEEDING:         1
CODEBUILD_INITIATOR:                GitHub-Hookshot/1c6af21
CODEBUILD_KMS_KEY_ID:               arn:aws:kms:ap-northeast-1:085041388644:alias/aws/s3
CODEBUILD_LOG_PATH:                 30ab0252-9d5b-4cf8-96a7-4c38b22d6df0
CODEBUILD_PUBLIC_BUILD_URL:         https://ap-northeast-1.codebuild.aws.amazon.com/project/eyJlbmNyeXB0ZWREYXRhIjoiSVlBb0dpNlEyYVBOZEhRTjJtazFDYTFYZVZualpXeS96R3FrODM1T1JtQXF5Z0l0UWFKV2pZMjA0UnlUTW44cm9WbWQxOEE2dStBdEsxQWtpL1FZcVVRQkl1SVlMQitjR1AvVFI3Zjh1UT09IiwiaXZQYXJhbWV0ZXJTcGVjIjoiMU1EWmVYZHVCaTI0dExPMyIsIm1hdGVyaWFsU2V0U2VyaWFsIjoxfQ%3D%3D/build/30ab0252-9d5b-4cf8-96a7-4c38b22d6df0
CODEBUILD_RESOLVED_SOURCE_VERSION:  661abba1941671b6c17d64bb422c6c567e9c2079
CODEBUILD_SOURCE_REPO_URL:          https://github.com/mocaberos/codebuild.git
CODEBUILD_SOURCE_VERSION:           pr/2
CODEBUILD_SRC_DIR:                  /codebuild/output/src180980763/src/github.com/mocaberos/codebuild
CODEBUILD_START_TIME:               1633091971530
CODEBUILD_WEBHOOK_ACTOR_ACCOUNT_ID: 83209034
CODEBUILD_WEBHOOK_BASE_REF:         refs/heads/master
CODEBUILD_WEBHOOK_EVENT:            PULL_REQUEST_CREATED
CODEBUILD_WEBHOOK_MERGE_COMMIT:     
CODEBUILD_WEBHOOK_PREV_COMMIT:      
CODEBUILD_WEBHOOK_HEAD_REF:         refs/heads/master
CODEBUILD_WEBHOOK_TRIGGER:          pr/2
HOME:                               /root
```

## PRをマージした場合
```text
AWS_DEFAULT_REGION:                 ap-northeast-1
AWS_REGION:                         ap-northeast-1
CODEBUILD_BATCH_BUILD_IDENTIFIER:   
CODEBUILD_BUILD_ARN:                arn:aws:codebuild:ap-northeast-1:085041388644:build/codebuild:644e4e41-3e58-41bc-a180-eb12b15046f2
CODEBUILD_BUILD_ID:                 codebuild:644e4e41-3e58-41bc-a180-eb12b15046f2
CODEBUILD_BUILD_IMAGE:              aws/codebuild/standard:5.0
CODEBUILD_BUILD_NUMBER:             4
CODEBUILD_BUILD_SUCCEEDING:         1
CODEBUILD_INITIATOR:                GitHub-Hookshot/1c6af21
CODEBUILD_KMS_KEY_ID:               arn:aws:kms:ap-northeast-1:085041388644:alias/aws/s3
CODEBUILD_LOG_PATH:                 644e4e41-3e58-41bc-a180-eb12b15046f2
CODEBUILD_PUBLIC_BUILD_URL:         https://ap-northeast-1.codebuild.aws.amazon.com/project/eyJlbmNyeXB0ZWREYXRhIjoiSVlBb0dpNlEyYVBOZEhRTjJtazFDYTFYZVZualpXeS96R3FrODM1T1JtQXF5Z0l0UWFKV2pZMjA0UnlUTW44cm9WbWQxOEE2dStBdEsxQWtpL1FZcVVRQkl1SVlMQitjR1AvVFI3Zjh1UT09IiwiaXZQYXJhbWV0ZXJTcGVjIjoiMU1EWmVYZHVCaTI0dExPMyIsIm1hdGVyaWFsU2V0U2VyaWFsIjoxfQ%3D%3D/build/644e4e41-3e58-41bc-a180-eb12b15046f2
CODEBUILD_RESOLVED_SOURCE_VERSION:  bf69116a32d322587d590c00228cf3eee9e77a9c
CODEBUILD_SOURCE_REPO_URL:          https://github.com/mocaberos/codebuild.git
CODEBUILD_SOURCE_VERSION:           bf69116a32d322587d590c00228cf3eee9e77a9c
CODEBUILD_SRC_DIR:                  /codebuild/output/src832993770/src/github.com/mocaberos/codebuild
CODEBUILD_START_TIME:               1633092135148
CODEBUILD_WEBHOOK_ACTOR_ACCOUNT_ID: 88621008
CODEBUILD_WEBHOOK_BASE_REF:         
CODEBUILD_WEBHOOK_EVENT:            PUSH
CODEBUILD_WEBHOOK_MERGE_COMMIT:     
CODEBUILD_WEBHOOK_PREV_COMMIT:      315bfa5910342a2fbba2d70a199c200e47ece696
CODEBUILD_WEBHOOK_HEAD_REF:         refs/heads/master
CODEBUILD_WEBHOOK_TRIGGER:          branch/master
HOME:                               /root
```

## githubで新しいリリースを作成した時(0.0.1タグ)
```text
AWS_DEFAULT_REGION:                 ap-northeast-1
AWS_REGION:                         ap-northeast-1
CODEBUILD_BATCH_BUILD_IDENTIFIER:   
CODEBUILD_BUILD_ARN:                arn:aws:codebuild:ap-northeast-1:085041388644:build/codebuild:d9d41907-4fde-429c-b06d-4e14dade1dfb
CODEBUILD_BUILD_ID:                 codebuild:d9d41907-4fde-429c-b06d-4e14dade1dfb
CODEBUILD_BUILD_IMAGE:              aws/codebuild/standard:5.0
CODEBUILD_BUILD_NUMBER:             13
CODEBUILD_BUILD_SUCCEEDING:         1
CODEBUILD_INITIATOR:                GitHub-Hookshot/1c6af21
CODEBUILD_KMS_KEY_ID:               arn:aws:kms:ap-northeast-1:085041388644:alias/aws/s3
CODEBUILD_LOG_PATH:                 d9d41907-4fde-429c-b06d-4e14dade1dfb
CODEBUILD_PUBLIC_BUILD_URL:         https://ap-northeast-1.codebuild.aws.amazon.com/project/eyJlbmNyeXB0ZWREYXRhIjoiSVlBb0dpNlEyYVBOZEhRTjJtazFDYTFYZVZualpXeS96R3FrODM1T1JtQXF5Z0l0UWFKV2pZMjA0UnlUTW44cm9WbWQxOEE2dStBdEsxQWtpL1FZcVVRQkl1SVlMQitjR1AvVFI3Zjh1UT09IiwiaXZQYXJhbWV0ZXJTcGVjIjoiMU1EWmVYZHVCaTI0dExPMyIsIm1hdGVyaWFsU2V0U2VyaWFsIjoxfQ%3D%3D/build/d9d41907-4fde-429c-b06d-4e14dade1dfb
CODEBUILD_RESOLVED_SOURCE_VERSION:  ad8869229df27c8daf89f8c74fc33aec575978db
CODEBUILD_SOURCE_REPO_URL:          https://github.com/mocaberos/codebuild.git
CODEBUILD_SOURCE_VERSION:           ad8869229df27c8daf89f8c74fc33aec575978db
CODEBUILD_SRC_DIR:                  /codebuild/output/src244870488/src/github.com/mocaberos/codebuild
CODEBUILD_START_TIME:               1633093122757
CODEBUILD_WEBHOOK_ACTOR_ACCOUNT_ID: 88621008
CODEBUILD_WEBHOOK_BASE_REF:         
CODEBUILD_WEBHOOK_EVENT:            PUSH
CODEBUILD_WEBHOOK_MERGE_COMMIT:     
CODEBUILD_WEBHOOK_PREV_COMMIT:      0000000000000000000000000000000000000000
CODEBUILD_WEBHOOK_HEAD_REF:         refs/tags/0.0.1
CODEBUILD_WEBHOOK_TRIGGER:          tag/0.0.1
HOME:                               /root
```

### CodeBuildフェーズ遷移
https://docs.aws.amazon.com/ja_jp/codebuild/latest/userguide/view-build-details.html#view-build-details-phases
![遷移図](https://github.com/mocaberos/codebuild/blob/master/images/build-phases.png)

### buildspec.yml構文
https://docs.aws.amazon.com/ja_jp/codebuild/latest/userguide/build-spec-ref.html#build-spec-ref-syntax
```
version: 0.2

run-as: Linux-user-name

env:
  shell: shell-tag
  variables:
    key: "value"
    key: "value"
  parameter-store:
    key: "value"
    key: "value"
  exported-variables:
    - variable
    - variable
  secrets-manager:
    key: secret-id:json-key:version-stage:version-id
  git-credential-helper: no | yes

proxy:
  upload-artifacts: no | yes
  logs: no | yes

batch:
  fast-fail: false | true
  # build-list:
  # build-matrix:
  # build-graph:
        
phases:
  install:
    run-as: Linux-user-name
    on-failure: ABORT | CONTINUE
    runtime-versions:
      runtime: version
      runtime: version
    commands:
      - command
      - command
    finally:
      - command
      - command
  pre_build:
    run-as: Linux-user-name
    on-failure: ABORT | CONTINUE
    commands:
      - command
      - command
    finally:
      - command
      - command
  build:
    run-as: Linux-user-name
    on-failure: ABORT | CONTINUE
    commands:
      - command
      - command
    finally:
      - command
      - command
  post_build:
    run-as: Linux-user-name
    on-failure: ABORT | CONTINUE
    commands:
      - command
      - command
    finally:
      - command
      - command
reports:
  report-group-name-or-arn:
    files:
      - location
      - location
    base-directory: location
    discard-paths: no | yes
    file-format: report-format
artifacts:
  files:
    - location
    - location
  name: artifact-name
  discard-paths: no | yes
  base-directory: location
  exclude-paths: excluded paths
  enable-symlinks: no | yes
  s3-prefix: prefix
  secondary-artifacts:
    artifactIdentifier:
      files:
        - location
        - location
      name: secondary-artifact-name
      discard-paths: no | yes
      base-directory: location
    artifactIdentifier:
      files:
        - location
        - location
      discard-paths: no | yes
      base-directory: location
cache:
  paths:
    - path
    - path
```
