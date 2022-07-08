# Application Module

## M30 설치 가이드 페이지 입니다.

기본적으로 M30의 하드웨어에 설치되어지는 소프트웨어에 대해서 가이드 하고 있습니다&#x20;

요구 환경요건는 다음과 같습니다&#x20;

* **Jetpack 5.0.0 이상 (Ubuntu 20.04 LTS 이상)**&#x20;
* **와이파이 또는 인터넷이 연결되있음을 확인**

M30을 위한 설치 단계는 크게 3가지 단계가 있습니다.

1. **Set-up**
2. **Build**&#x20;
3. **Execute**

### 1. Set-up

#### 1.1 설치 스크립트 파일 다운로드

시작하기 전에 반드시 설치 스크립트 파일을 먼저 다운로드 해주세요&#x20;

터미널을 열어주고 다음 스크립트 다운로드 코드를 입력해줍니다.&#x20;

로그인 ID : AngelRobotics-SW

PW(퍼블릭 토큰) : ghp\_YJZKQpMsD2s5UXILrlTjvu33TBEdVz3Y476P

{% hint style="info" %}
터미널를 여는 단축키는 Ctrl+Alt+t 입니다.
{% endhint %}

```
// 스크립트 파일 다운로드 
git clone https://github.com/AGR-SW/xavier_scripts.git
```

#### 1.2 Set-up 스크립트 실행

{% hint style="info" %}
Set-up은 네트워크 환경에 따라 통상적으로 5-20분까지 소요 될 수 있습니다.
{% endhint %}

처음 M30 소프트웨어를 설치위하기 위에서 셋팅 및 설치 하기 위한 명령어를 실행합니다.

```
. xavier_scripts/xavier_setup_script.sh
```

"Set-up completed !" 가 뜬다면 Set-up 은 완료입니다.&#x20;

### 2. Build

#### 2.1 Build 스크립트 실행&#x20;

Build 스크립트는 AM에서의 Jetpack GPIO,유저 앱, CM, 모바일 앱, 클라우드 등에 연동 하기위해서의 해당 소스 코드를 받고 빌드 하는 작업을 포함하고 있습니다.

아래 명령어를 통해 스크립트를 실행합니다.&#x20;

```
. xavier_scripts/xavier_build_script.sh
```



### 3. Execute

#### 3.1 Execute 스크립트 실행

&#x20;Execute 스크립트는 AM의 모든 기능을 가동시키기 위한 스크립트입니다.

아래의 명령어를 통해서 모든 노드를 실행합니다.

```
. xavier_scripts/xavier_execute_script.sh
```

