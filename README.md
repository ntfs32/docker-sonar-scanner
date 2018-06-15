# docker-sonar-scanner

- Using on gitlab runner:

```
sonarqube:
stage: build
image: notices/docker-sonar-scanner
script:

- |-
  sonar-scanner \
  -Dsonar.projectKey=projectKey \
  -Dsonar.projectName=projectName \
  -Dsonar.projectVersion=${CI_BUILD_REF_NAME} \
  -Dsonar.sources=. \
  -Dsonar.sourceEncoding=UTF-8 \
  -Dsonar.login=${SONAR_TOKEN} \
  -Dsonar.host.url=${SONAR_URL} \
  -Dsonar.scm.provider=git \
  -Dsonar.coverage.exclusions=. \
  -Dsonar.exclusions=**/dist/**,**/node_modules/**/*  
tags:
- tag1
```
