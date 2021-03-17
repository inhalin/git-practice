# Git Commands Details

## init

### OPTIONS

1. `-q` or `--quiet` : error와 warning 메시지만 출력하고 그외 메시지들은 전부 무시한다.

2. `--bare` : 빈 레포지토리를 만든다. 만약 GIT_DIR 환경이 설정되어있지 않으면 현재 작업중인 디렉토리로 설정된다.ctory.

3. `--object-format=<format>` : 레포지토리의 해시 알고리즘 포맷을 명시해준다. 올바른 포맷은 sha1 또는 sha256이고 기본값은 sha1이다. (sha256은 아직 초기단계로 테스트 목적으로만 사용.

4. `--template=<template_directory>`: 사용할 템플릿의 디렉토리를 명시해준다.

5. `--separate-git-dir=<git dir>` : 
    Instead of initializing the repository as a directory to either $GIT_DIR or ./.git/, create a text file there containing the path to the actual repository. This file acts as filesystem-agnostic Git symbolic link to the repository.

    If this is reinitialization, the repository will be moved to the specified path.

6. `-b <branch-name>` or `--initial-branch=<branch-name>` : 새로 생성되는 레포지토리의 초기 브랜치에 명시된 이름을 사용한다. 명시하지 않은 경우 기본값인 master를 사용한다.(브랜치 이름은 언제든지 init.defaulBranch 환경변수를 통해 변경할 수 있다.)

7. `--shared[=(false|true|umask|group|all|world|everybody|0xxx)]` : 깃 레포지토리를 다수의 유저가 공유할 때 옵션명을 통해 공유할 그룹을 명시해준다. `--shaerd`를 명시하면 환경변수 "core.sharedRepository"가 설정돼서 $GIT_DIR 밑에 파일과 디렉토리가 요청된 권한과 함께 만들어진다. 옵션에는 다음과 같은 값들이 있다. 옯션값을 명시하지 않으면 기본값은 `group`이다. 
    
    `umask (or false)` : umask(2)로 보고된 권한을 사용한다. `--shared`가 명시되지 않았을 때의 기본값이다.

    `group (or true)` : 그룹-쓰기전용 레포지토리로 만든다.

    `all (or world or everybody)` : `group`과 같지만 모든 유저가 레포지토리를 읽을 수 있게 한다.

    `0xxx` : 모든 파일은 0xxx의 8진수 모드를 가진다. 0xxx는 사용자의 umask(2) 값을 오버라이드한다. `0640`은 그룹-읽기전용 레포지토리를 생성한다. `0660`은 현재 사용자와 그룹에 그룹-읽기/쓰기 전용 레포를 만든다. 다른 사용자들은 접근할 수 없다.