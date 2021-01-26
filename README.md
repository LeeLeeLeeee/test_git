> # HEAD란?
> ![Alt text](/img/HEAD.PNG)
> # Branch란?
> ##### Branch란 각기 다른 코드를 효율적으로 작성하기 위한 가지들이다.
> ##### Branch로 작업 후 병합하기도 하고 task가 무산된 경우 삭제처리도 용이하다.
> ## Git branch 모델
> >
> > ## 메인브랜치 [master , develop]
> > * master 브랜치는 최종 배포 상태만 관리, 배포 번호를 태그에 기록하여 커밋
> > * develop 브랜치는 개발 진행용 브랜치
> > ## 피처브랜치 [feature]
> > feature 브랜치는 버그 수정, 새로운 기능등 모든 기능이 정상적으로 동작하는 지 확인
> ## Git branch 전환 [checkout ]
> ```
> git checkout <branchname>
> git checkout -b <branchname>의 경우 생성하면서 전환한다.
> ```
> ## Git branch 병합 [merge, rebase] 
> > ### merge
> > -----
> > merge
> ```
> git checkout <branchname>
> git checkout -b <branchname>의 경우 생성하면서 전환한다.
> ```
> > ## merge
> 
> ```
> 코드
> 
> 
> ```