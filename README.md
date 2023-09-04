# cpp-toy-server
C++를 사용한 서버 개발 학습용 레포지토리입니다.

[Drogon HTTP application framework](https://github.com/drogonframework/drogon)을 사용합니다.

## 환경 준비
* 패키지 관련 설치
```bash
sudo apt-get install -y gcc gcc-multilib g++ g++-multilib gdb gdbserver cmake libjsoncpp-dev uuid-dev zlib1g-dev openssl libssl-dev libmariadb3 libmariadb-dev libsqlite3-dev
```
* [Drogon 빌드 및 설치](https://github.com/drogonframework/drogon/wiki/ENG-02-Installation)
```bash
git clone https://github.com/drogonframework/drogon
cd drogon
git submodule update --init
mkdir build
cd build
cmake ..
make && sudo make install
```
* 디버그/릴리즈 설정: 빌드 시 다음 옵션 첨부 필요, 기본 값: 디버그
```bash
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake -DCMAKE_BUILD_TYPE=Debug ..
```
* 설치 후 위치
    * header: /usr/local/include/drogon
    * library: /usr/local/lib/libdrogon.a
    * tool: /usr/local/bin/drogon_ctl 
    * trantor header: /usr/local/include/trantor
    * trantor library: /usr/local/liblibtrantor.a
    
## 환경 생성 및 첫 빌드, 실행
* 환경 생성
```bash
drogon_ctl create project cpp-toy-project
```
* 첫 빌드 및 실행
```bash
echo '<h1>Hello Drogon!</h1>' >>index.html
cd build
cmake ..
make
./cpp-toy-project
```
* 졉속
```bash
curl 127.0.0.1:5555
```