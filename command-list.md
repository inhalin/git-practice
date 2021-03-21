# Git 명령어 리스트

## 시작하기

```sh
git init  # git 시작
git add . # 모든 파일 index에 올리기
git commit -m "<커밋 메시지>"
```

- `git add 파일1` 파일1을 스테이지에 추가
- `git commit` 스테이지에 있는 파일 커밋
- `git commit -a` add 명령 생략하고 바로 커밋. 변경/삭제파일 자동 스테이징, untracked files 커밋 안됨
- `git push [-u] [원격저장소 별명] [브랜치 이름]` 현재 브랜치에서 새로 생선한 커밋들을 원격저장소에 업로드. -u 옵션으로 브랜치 업스트림 등록
- `git pull` 원격저장소 변경사항을 워킹트리에 반영. git pull = git fetch + git merge
- `git fetch [원격저장소 별명] [브랜치 이름]` 원격저장소 브랜치와 커밋들을 로컬저장소와 동기화
- `git merge 브랜치이름` 지정한 브랜치의 커밋들을 현재 브랜치 및 워킹트리에 반영