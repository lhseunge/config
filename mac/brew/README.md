brew 백업 전 준비사항
homewbrew에서 백업은 bundle이라고 부릅니다.
bundle 기능을 사용하려면 homebrew/bundle 탭을 등록해야 합니다.

 

brew bundle 명령어를 실행하면 homebrew/bundle 탭이 자동으로 등록됩니다.

$ brew bundle --help
 

전체 탭 목록을 확인합니다.

$ brew tap
...
homebrew/bundle
homebrew/bundle 탭이 새로 추가된 걸 확인할 수 있습니다.

 

brew 백업
현재 설치된 모든 tap, cask, formulae를 리스트로 뽑아낸 후 현재 경로에 Brewfile을 새로 생성합니다.

# Brewfile 생성하기
$ brew bundle dump --describe
--describe 옵션은 생성한 Brewfile에 각 패키지를 설명하는 주석을 같이 달아줍니다.

 

생성할 Brewfile의 이름을 직접 정할 수도 있습니다.

# 지정된 이름의 Brewfile 생성하기
$ brew bundle dump --describe --file='Brewfile_20220724'
 

Brewfile 내용 확인
생성된 Brewfile 내용을 확인합니다.

$ brew bundle list
 

또는 cat 명령어로 Brewfile의 내용을 직접 확인할 수도 있습니다.

$ cat ./Brewfile
tap "acrogenesis/macchanger"
tap "aquasecurity/trivy"
tap "aws/tap"
...
brew "argo"
brew "argocd"
brew "autojump"
...
 

brew 복구
brew가 설치된 새 맥북에서 Brewfile을 옮긴 후 아래 명령어를 입력해서 복구를 실행합니다.

# 디폴트 파일명 Brewfile을 사용하여 설치
$ brew bundle install
# 특정 이름의 Brewfile을 사용하여 설치
$ brew bundle install --file Brewfile_20220724
Brewfile에 적혀있는 모든 tap, cask, formulae 패키지들이 한 번에 설치됩니다.
