> # Git branch
>
> > ## branch 란?
> >
> > branch란 분기를 의미한다.
> > 각 용도에 맞게 브랜치 즉 코드를 분리하여 협업 및 버전 관리에 도움을 줄 수 있는 기능
>
> ## Git branch 생성 [branch]
>
> ```
> git branch <branchname>
> ```
>
> ## Git branch 전환 [checkout]
>
> ```
> git checkout <branchname>
> git checkout -b <branchname>의 경우 생성하면서 전환한다.
> git checkout -- <filename> file을 되돌린다 <strong style='color:red'>주의해서 사용</strong>
> ```
>
> ## Git branch 병합 [merge, rebase]
>
> [merge, rebase 차이](https://brunch.co.kr/@anonymdevoo/7)
>
> > ### merge
> >
> > - 브랜치를 병합하는 명령어 만약 각 브랜치의 루트 커밋이 다를 경우 머지 커밋을 생성 후에 붙인다.
> > - 메인 혹은 유지할 브랜치로 전환하여 병합시킬 브랜치를 입력한다.
> > - 코드에 충돌이 날 경우 해결해줘야한다.
> >
> > ```
> > # git merge <mergered branch>
> > ```
> >
> > ## rebase
> >
> > - 브랜치를 병합하는 명령어 rebase 단어 뜻 그대로 정렬한다는 뜻이다.
> > - 브랜치를 하나의 브랜치로 재정립한다.
> > - 병합시킬 브랜치로 전환하여 메인 혹은 유지할 브랜치를 입력한다.
> > - 코드에 충돌이 날 경우 해결해줘야한다.
> >
> > ```
> > # git rebase <maintaining branch>
> > ```
> >
> > ## \*커밋 병합 rebase
