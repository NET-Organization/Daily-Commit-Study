# 👾 Git 사용법

## Git과 Github

Git은 "분산 버전 관리 시스템"으로, 개발 과정에서 **소스 코드의 변경 사항을 추적하고, 관리**하는 데 사용됩니다.

Git을 사용하면 코드의 버전 관리가 가능하고, 누가, 언제, 어떤 코드를 수정했는지 알 수 있기 때문에 협업하기 편리합니다.

따라서, Git을 사용하는 이유는 **개발할 때 편리하게 협업**할 수 있기ㄷ 때문입니다.


Github은 Git을 기반으로 한 웹 호스팅 서비스입니다. 더 편하게 Git 을 사용할 수 있도록 Github가 Git을 기반으로 온라인 서비스를 제공해준다고 생각하면 됩니다. 

Github를 사용하면 프로젝트를 쉽게 관리할 수 있고, 이슈 트래킹, Pull Request 등의 기능을 활용할 수 있습니다.

## 💡 초기설정
### 1. git 설치하기
[Git 설치](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-Git-%EC%84%A4%EC%B9%98)

### 2. github 계정 생성
[Github 계정 생성](https://github.com/)

### 3. git 버전 확인
git이 잘 설치되었는지 로컬 터미널에서 확인합니다.
```
git --version
```
잘 설치되었으면 아래와 같이 버전이 뜹니다. 안 뜨면 다시 설치해주세요!
<img width="383" alt="image" src="https://github.com/user-attachments/assets/44da4b19-0ea3-4e05-b957-01cc956fcd72">

### 4. 로컬에 github 계정 정보 등록하기
아래처럼 github 계정 정보를 등록해주세요.
```
git config --global user.name "Your Username"
git config --global user.email "your@email.com"

예시)
git config --global user.name cowboysj
git config --global user.email email@khu.ac.kr
```

아래 명령어로 잘 등록되었는지 확인할 수 있습니다.

```
git config -l
```
아래 사진처럼 뜨지 않으면 다시 등록해주세요.
<img width="399" alt="image" src="https://github.com/user-attachments/assets/60d636e3-cd80-42fa-bded-96006cb7fc00">

## ⚒️ git 사용하기 
### 1. 원격 저장소(Repository) 생성하기
자신의 프로필 > Repositories에 가서 `New`라는 버튼을 클릭하면 됩니다.

<img width="1079" alt="image" src="https://github.com/user-attachments/assets/89e59fe5-410a-499a-b2eb-9a0ba51f7ec8">

Repository 이름, 설명을 적어주고 몇 가지 항목들을 선택한 뒤 `Create Repository`를 눌러주면 됩니다.

<img width="891" alt="image" src="https://github.com/user-attachments/assets/24cd2d04-a7f4-4e79-9c07-3d35b94aa1c4">

- `public vs private` : 해당 Repository 공개/비공개 설정입니다. 특별한 사유가 아닌 이상 public을 권장합니다~!
- `Add a README file` : 자동으로 README 파일(Repository 소개하는 파일)을 만들어줍니다. (깃허브 사용이 처음이라면 선택 안 하고 시작하는 걸 추천드립니다.)
- `Add .gitignore` : 환경변수 파일 같이 로컬에는 있지만 github에는 올라가면 안 되는 파일들의 목록을 저장하는 파일입니다. 
- `Choose a license` : 해당 repository의 license를 고르는 항목입니다. 보통 MIT License를 많이 쓰며 굳이 선택 안 하셔도 됩니다. 

### 2. 로컬 저장소와 원격 저장소 연결하기
위에서 만든 원격 저장소를 로컬 저장소와 연결하려면 아래 명령어를 사용하면 됩니다.

vscode와 같은 프로그램을 사용한다고 했을 때, 새로 생성한 폴더를 열고, 터미널을 열어서 명령어를 입력하면 됩니다. 

아래 사진에서 파란색 부분의 링크를 복사합니다. (https://github.com.cowboysj/test.git)
<img width="974" alt="image" src="https://github.com/user-attachments/assets/be7683d8-3fe6-4c0a-a6cd-14e2b62e40b3">

```
git init
git remote add origin 붙여넣기
```
그럼 원래 폴더 안에 새로운 폴더가 하나 생기고, 연결이 완료됩니다.


```
git remote -v
```
위 명령어를 통해 연결이 잘 되었는지 확인할 수 있습니다. 

<img width="564" alt="image" src="https://github.com/user-attachments/assets/214c2458-f81c-4220-8a7a-8fb8281c51ec">

위 사진처럼 뜨면 연결이 잘 된 것입니다.

원격저장소의 파일을 컴퓨터로 복사해오려면 git clone을 사용하면 됩니다.

git clone을 사용하면 origin에는 기본적으로 클론해온 remote url이 저장되어 있습니다. (remote 안 해도 됨)

```
git clone 붙여넣기
```

### 3. SSH, 토큰
SSH KEY를 등록하면 git 연결을 더 빠르고 안전하게 할 수 있습니다.
자세한 내용은 https://github.com/KennethanCeyer/tutorial-git?tab=readme-ov-file#lock-ssh 를 참고해주세요.

토큰을 이용해 등록할 수도 있습니다.

깃허브에서 토큰을 발급받은 후, push할 때 터미널에 뜨는 창에 토큰을 입력해주세요. 
(토큰은 입력/붙여넣기 해도 보이지 않습니다. 그냥 입력하고 엔터 치면 입력된 것입니다.)

### 4. 변경 사항 업로드하기


> 변경 사항 업로드
```
전체 파일 추가 : git add  .

특정 파일 추가 : git add 파일 이름
```
> 커밋
커밋을 해야 staged 상태의 파일이 기록됩니다.

```
git commit -m "[Feat] : 회원가입 기능 구현"
```
> 특정 브랜치로 push하기

```
git push origin main (main 브랜치로 푸시)
```
git을 처음 써본다면 이 세 가지 명령어만 알고 있으면 됩니다!

1. 파일 수정 후 `git add .`
2. `git commit -m "커밋 메시지"`
3. `git push origin main`

## 🪵 브랜치 
git에서는 기본적으로 제공되는 main 브랜치 이외에도 여러 브랜치를 만들어 관리할 수 있습니다.

보통 git flow라는 방식으로 협업을 많이 하며, main 브랜치를 보호하기 위해 develop 브랜치를 만들고, 각 이슈별 브랜치를 파서 develop에 pr을 날리는 방식을 주로 씁니다.

[git flow 방식이란?](https://techblog.woowahan.com/2553/)

> 브랜치 생성 
```
git branch 브랜치명
```
deafult 브랜치가 main이라면 main을 기준으로 브랜치를 만듦니다.(새로운 브랜치에 main 코드가 들어가있음)
> 브랜치 확인
```
git branch 
```

> 내가 새로 만든 브랜치가 안 들어왔다면
```
git remote update 
```

>다른 브랜치로 이동
```
git checkout 브랜치
```

>브랜치 생성과 전환을 동시에 하기
```
git checkout -b 새로 만들 브랜치명
```


🔗 참고문헌
https://github.com/KennethanCeyer/tutorial-git?tab=readme-ov-file

https://modulabs.co.kr/blog/git-and-github-for-beginners/