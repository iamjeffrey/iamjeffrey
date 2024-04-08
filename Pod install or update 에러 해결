
1) sudo gem install cocoapods --user-install 시,
  Ignoring ffi-1.15.5 because its extensions are not built. Try: gem pristine ffi --version 1.15.5
1.11.3 오류가 발생
  1.1) sudo gem install ffi --version 1.15.5 --user-install

2) sudo gem install cocoapods --user-install 시 설치 되지 않은 경우
  2.1) ruby --version
          ruby 2.6.10p210 (2022-04-12 revision 67958) [universal.x86_64-darwin23]

  2.2) PATH 확인 후 없으면
      export PATH=$HOME/.gem/ruby/2.6.0/bin:$PATH

  2.3) sudo gem install cocoapods --user-install

3) brew install cocoapods 설치 시,
      Error: Failed to load formula: cocoapods
      cocoapods: unknown or unsupported macOS version: :dunno
      Warning: Treating cocoapods as a cask. 오류가 발생

  3.1) curl -fsSL -o install.sh https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
  3.2) brew install chruby ruby-install
  3.3) brew install cocoapods
       brew upgrade cocoapods
       
