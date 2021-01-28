> # Git Commit
>
> > ## Commit 이란?
> >
> > branch란 분기를 의미한다.
> > 각 용도에 맞게 브랜치 즉 코드를 분리하여 협업 및 버전 관리에 도움을 줄 수 있는 기능
> >
> > ## Git Commit 생성 [commit]
> >
> > ```
> > git branch <branchname>
> > ```
> >
> > ## Git Commit 합체(squash)!! [rebase]
> >
> > ```
> > git rebase -i HEAD~[num] //현재 HEAD commit 포함하여 num개까지 합체 모드!
> > p - 선택
> > s - 생략
> > ```
