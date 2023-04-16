---
layout: home
---

# TTY
리눅스에서 `tty`는 `터미널`을 의미하며, login tty는 로그인 화면을 표시하는 `가상 터미널`을 말합니다. 

## 가상터미널
login tty는 로그인을 위해 터미널 화면을 제공하는 가상 터미널을 의미합니다. 일반적으로 Ctrl + Alt + F1에서 `Ctrl + Alt + F6` 사이의 키를 눌러서 login tty를 사용할 수 있습니다. 

## 다중 사용자 환경 지원
리눅스는 다중 사용자 운영체제로, 여러 사용자가 동시에 시스템에 접속하여 작업을 수행할 수 있습니다. 가상 터미널인 tty는 다중 사용자 환경에서 각각의 사용자가 로그인하여 독립적인 쉘 환경을 제공할 수 있습니다.


## 비디오 터미널 및 시리얼 터미널 지원
tty는 비디오 터미널과 시리얼 터미널을 지원하므로, 서로 다른 유형의 터미널과 연결할 수 있습니다. 이는 리눅스의 이식성을 높이는 데 도움을 줍니다.

## 일관성 있는 사용자 인터페이스 제공
가상 터미널을 사용하면 모든 사용자 인터페이스가 `일관성` 있게 유지됩니다. 이는 사용자들이 시스템을 보다 쉽게 사용할 수 있도록 도와줍니다.

## 디버깅 및 시스템 관리에 유용
가상 터미널을 사용하면 시스템 관리자가 여러 개의 터미널을 사용하여 시스템 상태를 모니터링하고 디버깅할 수 있습니다. 이는 시스템 관리에 유용합니다.