
📚 Useful Mac Terminal Commands

Opens the current folder in Finder
open .

s much further:
    open index.html              # open in default browser
    open -a Safari index.html    # open in a specific app
    open -a "Visual Studio Code" .
    open https://github.com      # URLs work too
    open -R config.json          # reveal the file in Finder (highlighted)


## mdfind — Spotlight Lives in Your Terminal
    find 는 용량이 큰 드라이브에서는 검색이 느림.
    Spotlight has a command-line interface.

    mdfind "docker-compose.yml"

    Scope it to the current folder:
    mdfind -onlyin . "TODO"

    Find by name only:
    mdfind -name ".zshrc"

## screencapture — Screenshots Without Touching the Mouse
    You know Cmd+Shift+4
    screencapture -c            # full screen → straight to clipboard
    screencapture -i shot.png   # interactive selection → file
    screencapture -T 5 shot.png # 5-second timer (open that dropdown menu first)
    screencapture -w window.png # click a window, capture just it

    The -c flag is the daily driver where full screenshot directly to the clipboard, 
    no file cluttering your desktop, ready to paste into Slack.

<hr />



# Terminal에서 커맨드 실행 시 database is inaccessible 에러 : .zshrc
  -> 추가 : export TERMINFO=/usr/share/terminfo

# telnet
curl -v telnet://localhost:8080

# Android Simulator telnet token값을 텔넷 연결 후 입력.
cat /Users/<user>/.emulator_console_auth_token

- Available shell on Mac 
cat /etc/shells
  ->  /bin/bash
      /bin/csh
      /bin/dash
      /bin/ksh
      /bin/sh
      /bin/tcsh
      /bin/zsh

## Z shell
- Available shells
grep '^[^#]' /etc/shells

- Default shell
echo $SHELL
  --> /bin/zsh

- 마운트 드라이드 정보 보기
(echo "DEVICE PATH TYPE FLAGS" && mount | awk '$2="";1') | column -t

- Hidden file ls
ls -a | egrep "^\."

- IP address
ipconfig | grep "^en"
  --> enX: flags=xxxx<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500 
      ...
      enX: flags=xxxx<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500 

ifconfig et[X] | grep 'inet ' | sed -e 's/:/ /' | awk '{print "ip       : " $2}'
  --> ip       : 26.2.105.213

- Local ip
ifconfig lo0 | grep 'inet ' | sed -e 's/:/ /' | awk '{print "lo0       : " $2}'

- Clean user prompt
기본 
PS1="%n@%m %~ %# "
  --> 유저명@컴퓨터이름 ~ % 
PS1="%n@ %~ %# "
  --> 유저명@ ~ % [caret]
PS1="%n@ %1~ "
  --> 유저명@ ~ [caret]

- Figure out why App Transport Security denines a network connection 
 nscurl --ats-diagnostics --verbose https://example.com

- ATS Exceptions in Property list
  Property list Key : ( https://developer.apple.com/documentation/bundleresources/information_property_list/nsapptransportsecurity )
  {
      NSExceptionDomains =     {
          "example.com" =         {
              NSExceptionRequiresForwardSecrecy = false;
          };
      };
  }

# openssl command
$ openssl s_client -connect <url address>

# openssl path
$ type openssl 




