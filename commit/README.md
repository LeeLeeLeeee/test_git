# Git Commit

## Commit 이란?

변화에 대한 기록이다

## Git Commit 생성 [commit]

```
git commit -m "<message>"
```

## Git Commit 합체(squash)!! [rebase]

```
git rebase -i HEAD~[num] //현재 HEAD commit 포함하여 num개까지 합체 모드!
p - 선택
s - 생략
```

## Git Commit 마지막 수정

```
git commit -m "<message>" --amend
```
