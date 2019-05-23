# zzovlog
zzoPark's devlog
## 준비물
### 소스코드
```bash
# --recursive 옵션으로 submodule(backend, frontend)도 같이 clone함
git clone --recursive https://github.com/zzoPark/zzovlog.git
```
### 환경변수 등록
다른 방법(.env 파일, .bashrc 파일 그 외 기타등등)을 이용해도 된다
```bash
sudo vi /etc/environment
source /etc/environment
export ZZOVLOG_SECRET_KEY
...
```
잘 등록되었는지 docker-compose.yml 파일이 있는 곳에서 config로 확인
```bash
docker-compose config
```
## 실행방법
필자는 AWS EC2 Ubuntu 프리티어 인스턴스에서 실행함
```bash
# host에 db container를 위한 data directory 생성
cd zzovlog
mkdir db

# Docker 이미지 빌드 및 컨테이너 실행
docker-compose up -d

# django admin superuser 등록
docker exec -it zzovlog_backend_1 python3 manage.py createsuperuser
```
