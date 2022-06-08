

# Jenkins EC2


```
sudo apt update 
sudo apt install openjdk-11-jdk -y
```

자바 설치

```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

저장소 키 다운로드

```
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/" | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
```

패키지리스트에 추가

```
sudo apt-get update
sudo apt-get install fontconfig jenkins -y
```

젠킨스 설치

![002](./img/002.png)

```
"192.30.252.0/22"
"185.199.108.0/22"
"140.82.112.0/20"
```

AWS 보안그룹에서 8080 포트 ,GitHub API IP 액세스 허용

![001](./img/001.png)

Maven / Github Intergration plugin 설치

![003](./img/003.png)

젠킨스 프로젝트에서 GitHub hook trigger for GITScm polling 옵션 활성화

![004](./img/004.png)

 GIthub Repo > Settings > Webhooks에서 Webhook 생성

 - Payload URL: 젠킨스 접속 URL/github-webhook/
 - Content type: application/json

![005](./img/005.png)

커밋/푸시 후 GitHub Hook Log에서 확인
