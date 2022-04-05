# Install MariaDB in Ubuntu

## SQL 설치
```sudo apt-get install -y mariadb-server```

## SQL 실행
```sudo service mysql start```

## SQL 접속
```sudo mysql -u root```

## SQL 접속 후에 비밀번호 변경
* 최신버전의 MariaDB의 경우 리눅스 root 계정 정보를 사용하여 로그인하기 때문에 새로 변경하여 설정
* SQL 접속 후

```
set password = password('비밀번호');
flush privileges;
```

## 재시작 설정
```
sudo systemctl restart mysqld
```

## 외부 접속 허용
* 최신 MariaDB는 기본적으로 외부접속을 제한함
* 설정파일 변경 : https://blog.naver.com/timeless947/222332238079
* MariaDB 외부 권한
```
sudo mysql -u root  # 접속
```
* MariaDB 접속 
```
CREATE USER '아이디'@'%' IDENTIFIED BY '비밀번호';   # 사용자 생성
GRANT ALL PRIVILEGES ON 데이터베이스.* TO '아이디'@'%';  # 사용자 권한 주기
```

