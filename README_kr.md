# 기후자료 통계분석 — 실습 환경

이 수업의 실습 환경을 만들기 위한 가이드입니다.
아래 순서대로 환경 설정을 해주세요.

---

## 1. Miniforge 설치

Miniforge는 파이썬 패키지를 관리해 주는 `conda`를 설치하는 작은 프로그램입니다.
**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서 자기 컴퓨터에 맞는 설치 파일을 받으세요.

| 내 컴퓨터 | 설치파일 |
|---|---|
| 윈도우 | **Windows** — `x86_64` |
| 맥 (M1 / M2 / M3 / M4 칩) | **macOS** — `arm64 (Apple Silicon)` |
| 맥 (인텔 칩) | **macOS** — `x86_64 (Intel)` |
| 우분투 / 리눅스 | **Linux** — `x86_64 (amd64)` |

내 맥이 어느 쪽인지 모르겠다면, 화면 왼쪽 위 사과 메뉴 → **이 Mac에 관하여** →*칩* 항목을 확인하세요.

**이미 아나콘다가 깔려 있다면 지우지 마세요.** 그대로 두고 아래를 진행하면 됩니다.

### 윈도우

받은 `.exe` 파일을 실행합니다. *Welcome* 과 *License Agreement* 는 그대로 넘어가고,
다음 세 화면만 주의해 주세요.

**Select Installation Type** — **Just Me** 를 그대로 둡니다.

<img width="628" height="488" alt="캡처3" src="https://github.com/user-attachments/assets/374672e0-655b-4fb8-a672-ddadd398873b" />

**Choose Install Location** — 이 화면이 중요합니다.

기본 경로에는 윈도우 사용자 이름이 들어가는데, 이름이 한글이면 나중에 경로 문제가 생길 수 있습니다. 
경로 전체를 지우고 아래 경로를 입력하세요.

```
C:\Users\Public\miniforge3
```


<img width="615" height="486" alt="캡처" src="https://github.com/user-attachments/assets/3b243436-e1dc-4544-98b7-cb38feedb60d" />


**Advanced Installation Options** — **첫 번째와 네 번째만 체크**된 상태로 두고 Install 을 누르세요.

<img width="626" height="486" alt="캡처2" src="https://github.com/user-attachments/assets/fa34d3f0-4e0c-4fba-9658-c655a34c755d" />

첫 번째(Create shortcuts)를 빠뜨리면 **Miniforge Prompt** 가 생기지 않아 다음 단계로 넘어갈 수 없으니 꼭 확인하세요.

PATH 를 체크하지 않는 것은 의도한 것입니다. 
그래도 `conda` 는 잘 작동합니다.
설치가 끝나면 시작 메뉴에 Miniforge Prompt 가 생기는데, 그 창이 알아서 필요한 설정을 잡아 줍니다. 
PATH 에 등록하면 오히려 기존에 깔린 아나콘다나 파이썬과 충돌할 수도 있습니다.



### 맥 / 리눅스

### 맥

받은 `.pkg` 파일을 더블클릭하고 안내대로 진행하세요. **설치 경로는 기본값 그대로** 두시면 됩니다. 

윈도우와 달리 맥은 경로를 바꿀 필요가 없습니다.

설치가 끝나면 **터미널을 닫고 새로 여세요.** 줄 맨 앞에 `(base)` 가 보이면 성공입니다.

터미널이 어디 있는지 모르겠다면, 화면 오른쪽 위 돋보기(Spotlight)를 누르고 `터미널` 또는 `Terminal` 을 입력하면 됩니다.

### 리눅스

받은 `.sh` 파일을 터미널에서 실행합니다.

```
bash Miniforge3-Linux-x86_64.sh
```

라이선스는 아래 방향키로 넘긴 뒤 `yes`, 설치 위치는 엔터로 기본값을 그대로 받고,
마지막에 `conda init` 을 실행할지 물으면 **`yes`** 라고 답하세요.
그다음 터미널을 닫고 새로 열면 `(base)` 가 보입니다.



---

## 2. 실습 자료 내려받기

이 페이지 위쪽 초록색 **Code** 버튼 → **Download ZIP** → 압축을 풉니다.

압축은 반드시 풀어서 쓰세요. 압축 파일을 더블클릭해서 열린 창 안에서 실행하면 안 됩니다.

압축을 푼 폴더는 **바탕화면으로 옮겨 주세요.**

---


## 3. 실습 환경 만들기

먼저 터미널을 엽니다.

- **윈도우** — 윈도우 키를 누르고 `miniforge` 를 입력해서 **Miniforge Prompt** 를 실행합니다. (일반 명령 프롬프트가 아닙니다.)
  줄 맨 앞에 `(base)` 가 보이면 제대로 열린 것입니다.
- **맥 / 리눅스** — 터미널을 엽니다.

이제 실습 폴더로 이동합니다.

**윈도우 / 맥** — 경로를 직접 입력하는 대신 아래 방법을 쓸 수 있습니다.

1. `cd ` 를 입력합니다. (`cd` 뒤에 **한 칸 띄우기**)
2. 바탕화면의 실습 폴더를 **터미널 창 안으로 끌어다 놓습니다.** 경로가 자동으로 채워집니다.
3. 엔터를 누릅니다.

혹은 실습 폴더가 있는 경로를 직접 입력해도 됩니다.

```
cd C:\Users\사용자명\Desktop\climstat-2026     # 윈도우
cd ~/Desktop/climstat-2026                     # 맥 / 리눅스
```

제대로 왔는지는 `dir`(윈도우) 또는 `ls` 로 확인하세요. `.lock` 파일들이 보이면 맞습니다.



이제 자기 운영체제에 맞는 lock 파일로 환경을 만듭니다.

```
conda create -n climstat --file conda-win-64.lock        # 윈도우
conda create -n climstat --file conda-osx-arm64.lock     # 맥, 애플 실리콘
conda create -n climstat --file conda-osx-64.lock        # 맥, 인텔
conda create -n climstat --file conda-linux-64.lock      # 리눅스 / 우분투
```

lock 파일에는 필요한 패키지와 그 버전이 모두 적혀 있어서, 수강생 모두가 동일한 환경을 갖게 됩니다.

---


## 4. JupyterLab 실행

같은 창에서 아래 두 줄을 실행합니다.

```
conda activate climstat
jupyter-lab
```


<img width="1226" height="642" alt="실습환경 실행 및 주피터랩 실행" src="https://github.com/user-attachments/assets/59bcf1d7-b417-4d6d-8c5a-6869fb899adc" />


브라우저가 자동으로 열립니다.

두 번째 수업부터는 이렇게 하면 됩니다.

1. **Miniforge Prompt** 를 엽니다. (맥 / 리눅스는 터미널)
2. 위와 같은 방법으로 실습 폴더로 이동합니다. (`cd ` 입력 → 폴더 드래그 → 엔터)
3. `conda activate climstat` 과 `jupyter-lab` 을 실행합니다.

---


## 5. 환경 확인

**`00_setup_check.ipynb`** 를 열고 위에서부터 **모든 셀을 순서대로** 실행하세요.

각 셀은 확인 번호를 함께 출력합니다. 전부 통과했든 중간에 오류가 났든,
다 끝나면 **노트북을 저장(Ctrl+S)하고 그 `.ipynb` 파일 자체를 제출**해 주세요.


커널 이름은 `Python 3 (ipykernel)` 로 표시됩니다. 

---


## 문제가 생기면

### 자주 나오는 오류

| 오류 메시지 | 원인 |
|---|---|
| `conda is not recognized` | 시작 메뉴에서 Miniforge Prompt 를 열었는지 확인하세요. |
| `ModuleNotFoundError` | conda activate climstat 을 먼저 실행하세요. 창 맨 앞에 (climstat) 이 보여야 합니다. |

### 환경을 지우고 다시 만들고 싶을 경우

아래 두 줄이면 환경을 지우고 lock 파일에서 다시 만듭니다.
노트북이나 자료는 건드리지 않으니 부담 갖지 마세요.

```
conda env remove -n climstat
conda create -n climstat --file conda-win-64.lock
```

### climstat 환경에 패키지를 추가로 설치해야 할 경우

실습에 필요한 패키지는 모두 들어 있습니다. 그래도 다른 패키지가 필요하면
`pip install` 대신 아래처럼 설치하세요.

```
conda activate climstat
conda install -c conda-forge 패키지이름
```

---

## 이 저장소에 들어 있는 것

| 파일 | 용도 |
|---|---|
| `conda-*.lock` | 운영체제별 패키지 목록 (버전까지 고정) |
| `environment.yml` | lock 파일을 만들 때 쓴 패키지 목록 |
| `00_setup_check.ipynb` | 환경이 제대로 만들어졌는지 확인하는 노트북 |
| `waveletFunctions.py` | 수업 후반에 사용할 시계열 분석 함수 파일 |
| `data/` | 환경 확인용 샘플 자료 |


