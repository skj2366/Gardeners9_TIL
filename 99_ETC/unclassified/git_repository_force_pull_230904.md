# 원격 브랜치 강제 pull 하기 

새로운 프로젝트를 진행하게 되었는데, 22년 초에 잠깐 지원 한적이 있어서 프로젝트 세팅은 되어있다.

그런데 로컬 브랜치랑 꼬여있는지 원가 스테이지 되어있는 상황이 되어있고, 스테이지 된 내용 취소를 해도 사라지지 않는다.

그래서 원격 브랜치를 로컬 브랜치로 force pull 하는 방법을 채택 

- 원격 브랜치 최신화
  - `git fetch --all`
- 리셋 명령어 
  - `git reset --hard origin/master`
- pull 받기
  - `git pull origin master`

---

또 다른 방법 

`git pull origin [branchname] --allow-unrelated-histories`

