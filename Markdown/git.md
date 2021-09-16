# git

분산 버전 관리 도구

예전 피피티 마지막, 찐막, 진짜마지막 이렇게 은연중에 관리를 해 왔었던거임.



git은 변경 사항만을 저장한다! 파일을 저장하는게 아니고.

그래서 굉장히 가볍고 빠르다.

git은 분산 버전 관리 시스템 / github는 git기반의 저장소 서비스.



윈도우에 bashshell 깔아서 unix 명령어 사용할 수 있다.

---

## 명령어들

- ls : 현재 디렉토리의 파일 리스트
- mkdir : 디렉토리 만들기
- rm : 삭제
- rm -r : 디렉토리 삭제
- pwd : 현재 작업중인 디렉토리
- clear : 화면 지우기
- touch test.txt : test.txt.파일 만들기
- cd test : test디렉토리로 이동
- cd .. : 상위 폴더로 이동
- .은 현재 폴더를 의미함, ..은 상위 폴더이고
- git config --global --list : 현재 전역적으로 사용하는사람이 누가있는지

respository : 특정 디렉토리를 버전 관리하는 저장소

- git init : 로컬 저장소 생성. 기본적으로 숨김폴더로 생김

---

## git에 관하여

git에서 특정 버전으로 남긴다 = commit(커밋)한다. 3가지 영역을 바탕으로 동작.

1. Working Directory - 내가 작업중인 실제 디렉토리
2. Staging Area - 커밋으로 남기고 싶은, 특정 버전으로 관리하고픈 파일이있는곳
3. Repository - 커밋들이 저장되는곳

의 영역을 바탕으로 동작.

---

## 순서

1. git init
2. git add a.txt
3. git add . (해당폴더 것 다 add하는것)
4. git status
5. git commit -m "add b.txt" (메시지 남기며 커밋)
6. git log(확인용)
7. git diff A's id 1234 B's id 1234 (차이 확인하는것)
   1. git diff ddf9 625e (예를 들면 이렇게.) - 그럼 A 와 B가 무슨 차이가 발생했는지 보여줌

---

## 원격 저장소 연동 (깃허브와 연동)

- git remote add origin https://github.com/genesis7153/remote_repo.git
- 그 다음 git push -u origin master / origin이 원격저장소의 별명.
- 후 최초 브라우저를 이용해 인증 및 승인
- 한 번 -u 옵션을 이용해 연결해놓으면 그 다음부턴 사용 안해도 됨

---

## 클론

- git clone https://github.com/genesis7153/clone_repo.git
- 이렇게 하면 원격저장소의 깃이 로컬로 클론된다.
- 클론으로 생성되한 디렉터리는 이미 연결이 되어 있는 상태이기때문에
- remote add 안해도 된다. 바로 git push origin master 하면 된다.

## TIL(Today I Learned)

- 신입 개발자에게 요구되는 가장 큰 능력! 꾸준히 학습할 수 있나요?
- 매일 내가 배운 것을 마크다운으로 정리해서 문서화 하는 것.
- 코드도 포함해서!
- 바탕화면에 til 폴더를 만들고 repository로 설정
- readmd.md 파일 만들고 소개
- til이라는 이름의 github repository

---

