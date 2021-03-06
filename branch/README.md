# Git branch

## branch 란?

branch란 분기를 의미한다.
각 용도에 맞게 브랜치 즉 코드를 분리하여 협업 및 버전 관리에 도움을 줄 수 있는 기능

## Git branch 생성 [branch]

```bash
git branch <branchname>
```

## Git branch 전환 [checkout]

```bash
git checkout <branchname>
git checkout -b <branchname>의 경우 생성하면서 전환한다.
git checkout -- <filename> file을 되돌린다 <strong style='color:red'>주의해서 사용<strong>
```

## Git branch 병합 [merge, rebase]

[merge, rebase 차이](https://brunch.co.kr/@anonymdevoo/7)

## merge

- 브랜치를 병합하는 명령어 만약 각 브랜치의 루트 커밋이 다를 경우 머지 커밋을 생성 후에 붙인다.
- 메인 혹은 유지할 브랜치로 전환하여 병합시킬 브랜치를 입력한다.
- 코드에 충돌이 날 경우 해결해줘야한다.

```bash
git merge <mergered branch>
git merge --abort //되돌리기
```

## rebase

- 브랜치를 병합하는 명령어 rebase 단어 뜻 그대로 정렬한다는 뜻이다.
- 브랜치를 하나의 브랜치로 재정립한다.
- 병합시킬 브랜치로 전환하여 메인 혹은 유지할 브랜치를 입력한다.
- 코드에 충돌이 날 경우 해결해줘야한다.

```bash
git rebase <maintaining branch>
git rebase --continue //충돌 해결 후 재진행
```

## cherry-pick

- 체리픽 커밋은 다른 브랜치를 내가 작업한 브랜치로 합치는 커밋.
- 해당 브랜치의 특정 커밋 시점을 지정할 수 있음. (커밋 ID 앞 8자리)

```bash
#테스트 과정#
- cherry-pick 브랜치 생성 후 아래 작업 실행
1. file.txt 생성
2. txt 내부에 cherry-pick1 하고  add . 후  commit "1" ID => 12345678
3. txt 내부에 cherry-pick2 하고  add . 후  commit "2" ID => 12345679
4. txt 내부에 cherry-pick3 하고  add . 후  commit "3" ID => 12345680
5. txt 내부에 cherry-pick-error 하고  add . 후  commit "error" ID => 12345681

- cherry-pick으로 commit "3" 시점으로 돌아가려고 할 때.

1. 헤드를 다시 cherry-pick 브랜치 시작했던 지점으로 checkout
2. cherry-pick-correct 브랜치 생성 후 체크아웃 [git checkout -b "cherry-pick-correct"]
3. git cherry-pick 12345680 실행
4. cherry-pick 충돌 해결 후 => (git add. => git commit -m "커밋문구") 완료
```

## FAST-FOWARD 방식과 NON-FAST-FOWARD 방식
**위 두개의 병합 방식은 언제든 원하는 방식으로 진행할 수 있다**
- FAST-FOWARD 병합은 별도의 커밋을 생성하지 않고 병합하는 방식
- NON-FAST-FOWARD 병합은 별도의 커밋을 생성하여 병합하는 방식이다.


**`MASTER`는 커밋C, `DEV`는 커밋D, `bug-fix`는 커밋G인 레포지**
```bash
                 #MASTER  #DEV
[A]  -  [B]  -  [C]  -  [D] 
                   ↘ - [E] - [F] - [G] #bug-fix
```
**fast-foward**
- MASTER가 커밋C인 상태에서 DEV, bug-fix 브랜치를 병합할 때는 이력이 충돌하지 않아서 `fast-foward`방식으로 진행이된다.
```bash
    # fast-foward방식은 MASTER의 마지막 커밋에서 파생한 브랜치를 다시 MASTER에 병합하는 경우가 많음
    # 즉 오류 개선같이 급한 프로젝트에서 주로 사용한다.
    # 브랜치 이력을 남겨야한다면 non-fast-foward 방식으로 옵션을 지정하여 진행할 수도있다.
```

**non-fast-foward**
- `MASTER`를 `DEV`에 병합하고 다시 `bug-fix`에 병합하면 `non-fast-foward`방식으로 진행된다.
```bash
    # non-fast-foward방식은 MASTER의 끝과 병합할 브랜치의 시작이 다른 경우에 사용될 수 있다.
    # 새로운 커밋 [H]를 생성한 후 병합이 되는 방식이다.
    # non-fast-foward의 경우도 rebase로 하게되면 fast-foward 방식으로 진행할 수 있다.
```