---
title: "[M1 Mac] github.io 블로그 따라 만들기"

categories:
    - Github Blog

tags: 
    - GitHub
    - 깃허브 블로그
    - Jekyll
    - M1
    - 맥
---


말로만 계획했던 GitHub Blog를 만들었습니다!!  


M1을 탑재한 MacBook Air로 공부를 주로 할 겸, 맥북으로 github.io를 새로 만들었는데,  


생각보다 과정이 험난해 설치 과정을 다루며 GitHub Blog를 만드는 법을 작성하겠습니다.

##### 1. Homebrew
---
맥을 쓰는 이유 중 하나인 homebrew, 해당 포스트에서는 homebrew 설치 방법은 언급하지 않으니 <https://brew.sh/index_ko> 에 들어가셔서 설치해주세요.

##### 2. Rbenv 설치 및 Ruby 설치
---
Homebrew를 성공적으로 설치하셨으면, brew를 통해서 rbenv를 설치해야합니다.
```
brew update
brew install rbenv ruby-build
```
설치 후, rbenv로 관리되는 Ruby도 설치해야합니다. 버전들을 확인해봅시다.
```
rbenv install -l
```
21년 7월 28일 기준의 버전들입니다.  
![image](https://user-images.githubusercontent.com/63240477/127285559-39adbb44-d0b2-4a2a-860a-4809b7d49579.png)  
최신 버전인 3.0.2를 설치하겠습니다.
```
rbenv install 3.0.2
```
잘 설치가 되었는지 확인을 해보겠습니다.
```
rbenv versions
```
두 개가 잘 설치되었으면 다음과 같이 표시가 됩니다.

```
* system
  3.0.2 (set/by/Users/사용자이름/.rbenv/version)
```
잘 표시가 되었다면, global 버전을 3.0.2로 옮겨주셔야 합니다.
```
rbenv global 3.0.2
```
옮긴 후 다시 버전을 확인해보면
```
rbenv versions
```
다음과 같이 확인 할 수 있습니다!
```
  system
* 3.0.2 (set/by/Users/사용자이름/.rbenv/version)
```
그 후에는 PATH를 쉘의 설정파일에 추가를 해줘야합니다. 저는 oh my zsh를 사용하기에 .zshrc를 열어줍니다.
```
vim ~/.zshrc
```
파일을 열어주면 파일의 마지막 부분에 다음 코드를 복붙해주세요.  


참고로 vi 편집기에서 입력을 하려면 i를 누르시고(커서 위치부터 입력), 입력 후 ESC를 누르고 :wq를 입력해주세요.
```
  [[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval "$(rbenv init -)"
```
그 후에는 해당 코드를 적어서 변경 내용을 적용해주세요.
```
source ~/.zshrc
```
그러면 bundler를 설치할 준비가 끝났습니다.

##### 3. Bundler 및 jekyll 설치
---
bundler와 jekyll을 설치해줍니다.
```
gem install jekyll bundler
```
설치가 잘 이뤄졌는지 확인해봅시다.
```
bundler -v
jekyll -v
```
버전이 잘 뜬다면 잘 설치가 된 것입니다!  


설치가 다 되었으니 GitHub에서 블로그를 직접 만들어봅시다!




