# zzovlog
zzoPark's devlog
## 준비물
### 환경변수 등록
```bash
sudo vi /etc/environment
source /etc/environment
export ZZOVLOG_SECRET_KEY
...
```
## 실행방법
필자는 AWS EC2 Ubuntu 프리티어 인스턴스에서 실행함
```bash
# host에 db container를 위한 data directory 생성
mkdir db

# Docker 이미지 빌드 및 컨테이너 실행
docker-compose up -d

# django admin superuser 등록
docker exec -it zzovlog_backend_1 python3 manage.py createsuperuser
```
