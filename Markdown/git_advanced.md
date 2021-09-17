> 장쌤 : 미래에는 gpu의 역할이 커져서 단순연산을 많이 할 수 있는 쪽으로 발전될것이다. 왜냐하면 ai 빅데이터의 단순연산을 필요로 하기 때문이다. cpu는 복잡한 연산을 하는데 최적화되어있지만 병렬로 단순연산의 양을 늘리려면 gpu가 필수. 그리고 저장장치도 낸드플래시의 발달로 ssd가 나왔지만 그 다음 세대의 수많은 작은 데이터가 빨리 왔다갔다 할 수 있는 방식의 차세대 저장장치가 나온다면 ai시대를 평정할 것이다. ssd가 나는 빠르다고 생각했지만 여전히 발전의 여지는 있으니까! 저장장치가 가장 느린 속도이니까. 다음 트렌드를 이끌려면 그것이 중요한 역할을 할 것이다.

# 복습

링크는 []()

이미지는 ![]()

기울임체는 글자 양 끝에 *, *기울임*

굵은글씨는 글자 양 끝에 *2개,  **굵은글씨**

취소선은 글자 양 끝에 ~2개, ~~취소선~~

---

# Github Pages

username.github.io

origin을 삭제하고 싶다면 ? `git remote rm origin`

---

## Git_advanced

``git push origin master`` 밀어내는것(업로드)

``git pull origin master`` 가져오는것(다운로드)

git restore --staged {file} : git add(Working Directory에 있던걸 Staging Area로 올림) 했던걸 되돌린다. Staging Area에 들어갔던 것을 다시 Working Directory로 빼오는 것.

- ``git restore --staged test.txt``

git restore {file} : Working Directory에서 작업하던 것을 Repository에 있던 이전 최신버전의 상태로 돌린다. 기껏 저장했지만 다시 최신버전으로 돌아간다. - 잘 안쓸듯?

- ``git restore test.txt``

git reset --hard {c_id} : 커밋을 되돌리는것

- ``git reset --hard 670e``

---

## .gitignore

- git으로 버전관리 원하지 않는 파일 제외하는 역할.
- 중요 개인정보 같은 업로드 하지 않을 파일 적고 add . 활용하여 효율적으로.
- repository 생성하고 바로 만들어줘야 편하다.

.git 있는 메인 master repository 폴더에 .gitignore 파일을 만들고 그 안에다 파일명을 적어주면 된다.

하위 폴더에 있는 파일도 자동으로 적용된다.

`data/` 이렇게 적으면 data 폴더에 있는 모든 것을 ignore 하겠다는 것.

`*.png` 이러면 특정 확장자 모두를 ignore한다.

확장자 모두인데 특정 파일을 빼고 싶으면 그 다음에다 `!img2.png` 이렇게 하면 된다.

하지만 임시파일이나 os가 만드는 소스코드랑 상관 없는 파일들이 많기 때문에 템플릿을 이용한다. gitignore.io 에서 찾아서

---

# 브랜치

브랜치 : 특정 커밋을 가리키는 '포인터'

- 브랜치를 나눴다가 다시 합치는것을 merge라고 한다.
- 브랜치를 만들어야할까? 생각 들 땐 만드는 것을 추천.
- 포인터이기 때문에 용량을 많이 차지 안하기 때문에 파는 습관을 들이는것이 좋다.

##  Branch commands

- `git branch {branch name}` : 브랜치 생성
- `git checkout {branch name}` : 브랜치 이동
- `git branch` : 브랜치 목록
- `git branch -d {branch name}` : 브랜치 삭제

> bash에서 `code .` 치면 vscode 열린다.

병합을 진행할 때 서로 다른 이력에서 동일한 파일을 수정한 경우 충돌이 발생할 수 있다. 이 경우에는 반드시 직접 수정을 해야한다. 

충돌이 발생한 것은 오류가 발생한 것이 아니라 이력이 변경되는 과정에서 반드시 발생할 수 있는 것이다.

현업에서는 merge day가 있다. 한번에 배포하지마 하고 묶는 날

## Merge

`git merge login` : login 브랜치로 병합하기

master브랜치는 쭉 당겨와서 거저 먹었기 때문에 fast forward 머지라고 한다.

`git log --graph` : 브랜치 머지 그래프 보기

`git log --graph --oneline` : 브랜치 머지 간단 그래프 보기

## 협업 with PR

GitHub의 pull request로 코드를 합칠것인지 요구하여 수용하는 절차를 거침.

## Git Flow

현업에서는 main test release 이렇게 여러개 branch로 일 한다.

- master(main) : 배포 가능한 상태의 코드 ex) 클라이언트 라이브버전
- develope(main) : 주 개발 ex) 다음 패치 개발
- feature branches(supporting) : 기능별 ex)신규챔피언 세나 업데이트
- release branches(supporting) : 개발 완료 이후 테스트 ex)5.24a, 4.24b
- Hotfixes(supporting) : 긴급 버그 픽스 ex)긴급 챔피언 선택금지

