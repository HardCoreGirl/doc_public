# Install Jenkins in Ubuntu

## In Docker

### Install Jenkins
```
docker pull jenkins/jenkins:lts
```

### Run Jenkins
```
docker run -d -p 8090:8080 -v /jenkins:/var/jenkins_home --name myjenkins -u root jenkins/jenkins:lts
```
* -p : jenkins 컨테이너의 8080포트를 로컬의 8090 포트와 매핑
* -v : 컨테이너의 /var/jenkins_home을 로컬의 /jenkins 디렉토리와 공유
* --name : 컨테이너에 myjenkins라는 이름 주어짐
* -u : root의 권한을 줌

### Docker 실행여부
```
docker ps
```

### Jenkins 초기 실행 비밀번호 확인
* 도커 모드 돌입
```
docker exec -it myjenkins /bin/bash
```
* 도커 셀 실행
```
cat /var/jenkins_home/secrets/initialAdminPassword
```


