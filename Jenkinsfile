apiVersion: build.openshift.io/v1
kind: BuildConfig
metadata:
  labels:
    build: php-simple-app-pipeline
  name: php-simple-app-pipeline
  namespace: pipeline-cicd
spec:
  failedBuildsHistoryLimit: 5
  nodeSelector: {}
  output: {}
  postCommit: {}
  resources: {}
  runPolicy: Serial
  source:
    git:
      ref: master
      uri: https://gitn.svc.sigma.host/sigma/paas/openshift/pipelineCICD.git
    sourceSecret:
      name: git-repo-secret
    type: Git
  strategy:
    jenkinsPipelineStrategy:
      env:
      - name: GIT_SSL_NO_VERIFY
        value: "true"
      jenkinsfilePath: Jenkinsfile
    type: JenkinsPipeline
  successfulBuildsHistoryLimit: 5
