---
title: "2025년 기준 GitHub 블로그 구축기 -1 (실패와 해결 완전 정리)"
date: 2025-07-27 15:45:00 +0900
categories: [Git, GitHub blog]
tags: [Jekyll, Chirpy]
published: true
---

여러 블로그를 참고해서 GitHub 블로그 만들기에 대한 여정을 담았습니다.
> GitHub 블로그 만들기 
> 겪은 시행착오와 해결법
<!--more-->

---
# GitHub 설정

## 1. **GitHub 회원가입하기**

GitHub에서 Sign up for GitHub를 눌러 회원가입 절차를 시작합니다.ee
이메일과 비밀번호 등을 입력하고 나면 Launch code를 입력해야 합니다.
가입시 입력한 이메일의 받은 메일함에서 Launch code를 확인하셔서 입력하시고 간단한 설문조사를 마치고 나면 회원가입 완료! GitHub Sign up 절차는 언제봐도 깔끔하고 멋지네요.



## 2. **Repository(저장소) 생성하기**

웹사이트의 소스 코드를 저장할 공간을 만들어 보겠습니다. R> [!WARNING]
> [!WARNING]
epository는 프로젝트의 소스코드를 관리하기 위한 저장소입니다.

메인화면 좌측 상단의 Create repository를 클릭하고 각 항목을 아래와 같이 입력합니다.


Repository name : USERNAME.github.io를 입력합니다.
> [!WARNING]
> 꼭 아래 조건을 지켜야 합니다:
> - 이름은 꼭 **username.github.io** 형식이어야 합니다  
> - `username`은 네 GitHub 아이디와 **정확히 일치**해야 합니다
<!-- > ??? 꼭 	•	이름은 꼭 **username.github.io**로 해야 함 (username은 네 깃허브 아이디와 동일해야 함)
로 해야하는지??? -->

Public/Private : 저장소를 타인에게 공개할지 비공개할지 설정합니다. 여기서는 Public을 선택합니다.
Add a README file : 저장소를 생성할 때 README.md 파일을 같이 만들지 여부입니다. 여기서는 ✅합니다.

그 외 다른 설정들이 있으나 건드리지 않고 넘어가겠습니다. 화면 맨 아래 Create repository 버튼을 눌러 저장소를 생성합니다.


## 3. Git clone 하기
저장소를 처음 만들면 README.md 파일만 덩그러니 있습니다. 이제 이 저장소에서 GitHub 블로그를 만드는데 필요한 코드를 관리할텐데요, 인터넷 환경보다는 본인의 PC에서 작업하는 게 더 편하기 때문에 원격 저장소와 로컬 PC를 연결하고 원격 저장소의 데이터를 로컬로 복사해오는 과정이 필요합니다. 이를 clone 이라고 합니다.


GitHub 저장소 화면의 Code 버튼을 누르면 그림과 같이 지금 저장소의 데이터를 복사하기 위한 URL이 표시됩니다. URL을 복사하고 명령 프롬프트를 실행합니다.
> [!WARNING]
> 명령 프롬프트는 윈도우 키를 누르시고 cmd를 입력해 실행하실 수도 있습니다.

아마 C:\Users\사용자명> 처럼 표시될텐데, 저 경로의 폴더를 열어놓은 상태라고 이해하시면 됩니다. 여기서 화면에 컴퓨터가 이해할 수 있는 명령을 적으면 실행되는 것이죠.(이름이 명령 프롬프트인 이유!) git 폴더를 만들고 git clone 명령을 입력해 보겠습니다.

<pre><code>```bash
mkdir git
cd git
git clone https://github.com/ita-bility/ita-bility.github.io
```
</code></pre>

```console
C:\Users\kiyun>mkdir git
C:\Users\kiyun>cd git
C:\Users\kiyun\git>git clone https://github.com/ita-bility/ita-bility.github.io
'git'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.
```



'git'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.
git이 무슨 의미인지 모르겠다는 건데요, PC에 Git이 설치되어 있지 않아서 컴퓨터가 명령을 이해하지 못한 것입니다. 우선 Git을 설치해야겠네요.

Git을 아직 설치하지 않으셨다면 여기를 참고하셔서 설치 후 이어서 진행해주세요.

git이 설치되어 있다면 아래와 같은 내용이 나올 겁니다.

git clone https://github.com/ita-bility/ita-bility.github.io
Cloning into 'ita-bility.github.io'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
그리고 해당 경로로 가보면 파일이 잘 복사되어 있는걸 확인할 수 있습니다.

4. 로컬 Git에 새로운 파일 생성하기
로컬 Git에 새로운 파일을 만들어 보겠습니다. 폴더 안에 새 텍스트 파일을 만들고 Hello world를 입력한 뒤 저장합니다. 파일명은 Hello world.html로 하겠습니다. 그리고 파일 확장자를 txt에서 html로 바꿔줍니다.

확장명을 변경해도 사용할 수 있으니 바꿔주세요.

파일을 실행하면 웹브라우저에 Hello world가 떠있는 화면이 보이실 겁니다.

5. GitHub에 수정사항 반영하기
Hello world.html 파일을 만들었지만 로컬 PC에만 만들어졌을 뿐입니다. 작업한 내용을 GitHub에 저장하기 위해 아래 순서대로 진행해 보겠습니다.

변경사항 저장
변경사항 확정
원격 저장소에 업로드
1. 변경사항 저장
변경사항을 저장하기 위해 명령 프롬프트로 돌아가 아래와 같이 입력합니다.

cd ita-bility.github.io
git add -A
변경사항을 staging(저장을 확정하기 전 중간 단계)에 저장하되, 변경된 모든(-A, All) 내용을 저장한다는 명령어입니다.

2. 변경사항 확정


## 📌 블로그 특징
- 무료로 운영 가능
- 마크다운으로 글 작성
- 테마 꾸미기도 쉬움

---

## 🛠 앞으로 해보고 싶은 것
- [ ] 글에 이미지 넣기
- [ ] 코드 블럭 보여주기
- [ ] 다크모드 스타일 바꾸기
- [ ] 구독 버튼 만들기



### 출처
https://tired-o.github.io/posts/github-blog-1/
https://wlqmffl0102.github.io/posts/Making-Git-blogs-for-beginners-1/#google_vignette

---

고맙습니다 🙏  
곧 새로운 글로 돌아올게요!