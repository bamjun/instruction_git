# 깃 & 깃허브  

## $$\color{purple}\fbox{\Huge \color{pink}{git 명령어}}$$  
- 현재 환경에 설정된 유저와 이메일 조회하기  
  - 유저 확인하기  
    &darr; `\` &darr; `bash shell`
    ```bash
      git config --global user.name
    ```

  - 유저 변경하기  
    - git config --global user.name [변경할이름]  

    &darr; `\` &darr; `bash shell`
    ```bash
      git config --global user.name change
    ```

    ![alt text](images/markdown-image-1.png)  

  - 이메일 확인하기  
    &darr; `\` &darr; `bash shell`
    ```bash
      git config --global user.email
    ```

  - 이메일 변경하기  
    - git config --global user.email [변경할이메일]  

    &darr; `\` &darr; `bash shell`
    ```bash
      git config --global user.email change@change.com
    ```

    ![alt text](images/markdown-image-2.png)  

<br>  

<br>  

Windows 환경에서 Git 사용자 이름과 이메일 주소를 확인하는 방법은 명령 프롬프트(Command Prompt) 또는 Git Bash와 같은 터미널을 사용하는 것입니다. 이 정보는 Git의 전역(global) 설정 또는 특정 저장소(repository)의 로컬(local) 설정에 저장됩니다. 다음 단계에 따라 사용자 이름과 이메일을 확인할 수 있습니다.

### 전역 사용자 이름과 이메일 확인하기

1. **명령 프롬프트(Command Prompt) 또는 Git Bash 열기**: 검색을 통해 "cmd" 또는 "Git Bash"를 찾아 실행합니다.
   
2. **Git 전역 사용자 이름 확인**: 다음 명령어를 입력합니다.
   ```sh
   git config --global user.name
   ```
   이 명령은 전역 설정에 저장된 Git 사용자 이름을 출력합니다.

3. **Git 전역 이메일 확인**: 다음 명령어를 입력합니다.
   ```sh
   git config --global user.email
   ```
   이 명령은 전역 설정에 저장된 Git 사용자 이메일을 출력합니다.

### 특정 저장소의 사용자 이름과 이메일 확인하기

Git은 특정 저장소에 대해 다른 사용자 이름과 이메일 주소를 설정할 수 있습니다. 이는 전역 설정보다 우선 적용됩니다. 특정 저장소의 사용자 이름과 이메일 주소를 확인하려면, 해당 저장소의 디렉토리로 이동한 후 다음 명령어를 실행합니다.

1. **저장소 디렉토리로 이동**: `cd` 명령어를 사용해 해당 Git 저장소 디렉토리로 이동합니다.
   
2. **로컬 사용자 이름 확인**: 다음 명령어를 입력합니다.
   ```sh
   git config user.name
   ```
   이 명령은 현재 저장소에 설정된 사용자 이름을 출력합니다.

3. **로컬 이메일 확인**: 다음 명령어를 입력합니다.
   ```sh
   git config user.email
   ```
   이 명령은 현재 저장소에 설정된 사용자 이메일을 출력합니다.

### 설정 변경하기

Git 사용자 이름이나 이메일 주소를 변경하려면, `git config` 명령어에 `--global` 옵션을 사용하여 전역 설정을 변경하거나, 특정 저장소에서 이 옵션을 생략하여 로컬 설정을 변경할 수 있습니다. 예를 들어:

- **전역 사용자 이름 변경**:
  ```sh
  git config --global user.name "새 사용자 이름"
  ```
- **전역 이메일 변경**:
  ```sh
  git config --global user.email "새 이메일 주소"
  ```
- **로컬 사용자 이름 변경** (특정 저장소에서):
  ```sh
  git config user.name "새 로컬 사용자 이름"
  ```
- **로컬 이메일 변경** (특정 저장소에서):
  ```sh
  git config user.email "새 로컬 이메일 주소"
  ```

이렇게 설정을 변경하면, 이후에 수행되는 커밋에서 변경된 사용자 정보가 사용됩니다.

<br>  

--- 

<br>  

## $$\color{purple}\fbox{\Huge \color{pink}{up}}$$  
- `up` 파일만들기  

  &darr; `\` &darr; `v`
  ```bash
  #!"C:\Program Files\Git\git-bash.exe"

  if [ -z "$1" ]; then
      echo "커밋 메시지를 입력하세요."
  else
      git add .
      git commit -m "$1"
      git push
  fi
  ```
  <br>  

- github 로 푸쉬 하기위한 파일.  
  - 사용방법  
    - 터미널에서 . up [커밋 메세지]

    &darr; `\` &darr; `bash shell`
    ```bash
    . up test
    ```  

    <img src="images/markdown-image-3.png">

    <br>

  - `up` 파일설명
  
> 이 스크립트는 Git을 사용하여 변경된 모든 파일을 스테이지(stage)하고, 사용자가 제공한 커밋 메시지로 커밋(commit)한 뒤, 원격 저장소(remote repository)에 푸시(push)하는 자동화 작업을 수행하는 Bash 스크립트입니다. 스크립트는 Windows 시스템에서 Git Bash를 통해 실행되도록 설정되어 있습니다. 각 부분에 대한 자세한 설명은 다음과 같습니다:

1. `#!"C:\Program Files\Git\git-bash.exe"`: 이 라인은 "shebang" 또는 "hashbang"이라 불리며, 스크립트 파일이 실행될 때 사용할 인터프리터의 경로를 지정합니다. 여기서는 Windows 시스템에 설치된 Git Bash의 경로를 지정하여, 이 스크립트가 Git Bash를 사용하여 실행되어야 함을 나타냅니다.

2. `if [ -z "$1" ]; then`: 이 조건문은 스크립트에 전달된 첫 번째 인자(`$1`)가 비어 있는지 확인합니다. `-z` 플래그는 문자열의 길이가 0인지 테스트합니다. 즉, 사용자가 커밋 메시지를 입력하지 않고 스크립트를 실행했는지 확인합니다.

3. `echo "커밋 메시지를 입력하세요."`: 사용자가 커밋 메시지를 입력하지 않았다면, 사용자에게 커밋 메시지 입력을 요청하는 메시지를 출력합니다.

4. `else`: 사용자가 커밋 메시지를 입력했을 경우 실행됩니다.

    - `git add .`: 현재 디렉토리의 모든 변경 사항(신규 파일, 수정된 파일, 삭제된 파일)을 스테이징 영역에 추가합니다.
    - `git commit -m "$1"`: 사용자가 입력한 커밋 메시지(`$1`)를 사용하여 스테이징 영역에 추가된 변경 사항들을 커밋합니다.
    - `git push`: 최근 커밋을 현재 브랜치의 원격 저장소에 푸시합니다.

5. `fi`: `if` 조건문의 끝을 나타냅니다.

이 스크립트는 사용자가 커밋 메시지를 입력하지 않으면 경고 메시지를 출력하고, 입력했다면 해당 메시지로 변경 사항을 커밋한 후 원격 저장소에 푸시하는 간단하면서도 효율적인 자동화 과정을 제공합니다. 사용하기 전에 Git이 설치되어 있어야 하며, Git 저장소에서 실행되어야 합니다.

스크립트에서 사용되는 위치 매개변수(Positional Parameters)는 스크립트에 전달된 인자들을 참조하는 데 사용되는 특별한 변수입니다. 이들은 스크립트가 호출될 때 설정되며, 인자의 순서에 따라 `$1`, `$2`, `$3` 등과 같이 번호가 매겨집니다. 예를 들어, `$1`은 첫 번째 인자, `$2`는 두 번째 인자를 나타냅니다. 위치 매개변수를 사용하면 스크립트가 외부에서 전달받은 값에 따라 동작을 달리 할 수 있게 됩니다.

### 위치 매개변수의 종류

- `$0` - 스크립트의 이름 또는 스크립트를 호출하는 명령어. 스크립트 내부에서 이를 참조하면, 스크립트 자체의 이름을 얻을 수 있습니다.
- `$1` ~ `$9` - 첫 번째부터 아홉 번째까지의 인자를 나타냅니다. 스크립트에 전달된 각 인자는 이러한 변수를 통해 접근할 수 있습니다.
- `${10}`, `${11}`, ... - 열 번째 이후의 인자를 참조할 때는 중괄호 `{}`를 사용합니다. 예를 들어, 열 번째 인자는 `${10}`으로 참조합니다.
- `$#` - 스크립트에 전달된 인자의 총 개수를 나타냅니다.
- `$*` - 스크립트에 전달된 모든 인자를 하나의 문자열로 나타냅니다. 인자 사이는 IFS(Internal Field Separator) 환경 변수의 첫 번째 문자(기본값은 공백)로 구분됩니다.
- `$@` - 스크립트에 전달된 모든 인자를 별도의 문자열로 나타냅니다. 각 인자가 따옴표로 둘러싸여 인용됩니다. 이는 `$*`와 비슷하지만, 인자 사이의 공백을 보존하는 데 유용합니다.

### 예제

다음은 위치 매개변수를 사용한 간단한 스크립트 예제입니다:

```bash
#!/bin/bash

echo "스크립트 이름: $0"
echo "첫 번째 인자: $1"
echo "두 번째 인자: $2"
echo "인자 총 개수: $#"
echo "모든 인자(*): $*"
echo "모든 인자(@): $@"
```

이 스크립트를 `example.sh`라는 이름으로 저장하고, 다음과 같이 실행한다고 가정해 보겠습니다:

```bash
./example.sh arg1 arg2 arg3
```

출력은 다음과 같을 것입니다:

```
스크립트 이름: ./example.sh
첫 번째 인자: arg1
두 번째 인자: arg2
인자 총 개수: 3
모든 인자(*): arg1 arg2 arg3
모든 인자(@): arg1 arg2 arg3
```

위치 매개변수를 이용하면 스크립트가 보다 유연하게 동작하도록 만들 수 있으며, 사용자로부터 입력 받은 값에 따라 다양한 작업을 수행할 수 있습니다.

<br>

---  


