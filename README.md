 # HEAD란?

 ![Alt text](/img/HEAD.PNG)

 # Branch란?

 ##### Branch란 각기 다른 코드를 효율적으로 작성하기 위한 가지들이다.

 ##### Branch로 작업 후 병합하기도 하고 task가 무산된 경우 삭제처리도 용이하다.

 ## Git branch 모델

 ## 메인브랜치 [master , develop]

 - master 브랜치는 최종 배포 상태만 관리, 배포 번호를 태그에 기록하여 커밋
 - develop 브랜치는 개발 진행용 브랜치

 ## 피처브랜치 [feature]

 feature 브랜치는 버그 수정, 새로운 기능등 모든 기능이 정상적으로 동작하는 지 확인

 # GIT LOG 
 - GIT LOG는 HEAD가 있는 브랜치의 커밋 히스토리를 조회하는 기능이다.
 - 특별한 옵션이 없을 경우 commit ID, 작성자, 커밋 시간, 커밋 내용이 커밋 시간 순으로 내림 차순으로 나온다.

 ## GIT LOG 유용한 OPTION
|명령어|기능|
|------|----|
|-p(--patch)|각 커밋의 diff를 보여준다.|
|--stat|각 커밋의 통계를 포함하여 보여준다.|
|--pretty|log의 포맷을 지정한다|
|--graph|log의 dept를 그래프 형식으로 보여준다.|

### --pretty:format="<option>" 종류
|옵션|기능|
|------|----|
|%H|커밋 해시|
|%h|짧은 길이 커밋 해시|
|%T|트리 해시|
|%t|짧은 길이 트리 해시|
|%P|부모 해시|
|%p|짧은 길이 부모 해시|
|%an|저자 이름|
|%ae|저자 메일|
|%ad|저자 시각 (형식은 –-date=옵션 참고)|
|%ar|저자 상대적 시각|
|%cn|커미터 이름|
|%ce|커미터 메일|
|%cd|커미터 시각|
|%cr|커미터 상대적 시각|
|%s|요약|

```
    git log -p
    git log --stat
    git log --pretty=format:"%h - %an : %ad (%s)" # 출력 형식 => cfb9500 - LeeLeeLeeee : Tue Feb 16 00:50:37 2021 +0900 (feat : merge cherry-pick branch)
    git log --pretty=format:"%h - %an : %ad (%s)" --graph
```


