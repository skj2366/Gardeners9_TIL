# windows OS에서 Bun 사용해보기 

1. WSL 에서 실행 
   1. 아직 windows 환경에서 사용 불가능 

2. `sudo apt install unzip` 
   1. unzip 설치 
3. `curl https://bun.sh/install | bash`
   1. Bun 설치 

`bun --help` 명령어로 번 설치 확인 

`bun create-react-app [프로젝트 명]` 리액트 프로젝트 생성 


## WSL에 Node.js 설치가 되지 않으면 동작하지 않는다 

윈도우 로컬에 설치된 node에 접근 X 

https://learn.microsoft.com/ko-kr/windows/dev-environment/javascript/nodejs-on-wsl

해당 페이지를 따라 nvm 및 node 설치 
