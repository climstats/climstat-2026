# 기후자료 통계분석 — 실습 환경

이 수업의 실습에 필요한 모든 것이 들어 있습니다.
**첫 수업 전까지** 아래 순서대로 환경 설정을 마쳐 주세요. 20분 정도 걸리며,
대부분은 내려받는 시간입니다.

---

## 1. Miniforge 설치

Miniforge는 파이썬 패키지를 관리해 주는 `conda`를 설치하는 작은 프로그램입니다.
**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서
자기 컴퓨터에 맞는 설치 파일을 받으세요.

| 내 컴퓨터 | 눌러야 할 것 |
|---|---|
| 윈도우 | **Windows** — `x86_64` |
| 맥 (M1 / M2 / M3 / M4 칩) | **macOS** — `arm64 (Apple Silicon)` |
| 맥 (인텔 칩) | **macOS** — `x86_64 (Intel)` |
| 우분투 / 리눅스 | **Linux** — `x86_64 (amd64)` |

내 맥이 어느 쪽인지 모르겠다면, 화면 왼쪽 위 사과 메뉴 → **이 Mac에 관하여** →
*칩* 항목을 확인하세요.

**이미 아나콘다가 깔려 있다면 지우지 마세요.** 그대로 두고 아래를 진행하면 됩니다.

### 윈도우

받은 `.exe` 파일을 실행합니다. *Welcome* 과 *License Agreement* 는 그대로 넘어가고,
다음 두 화면만 주의해 주세요.

**Select Installation Type** — **Just Me** 를 그대로 둡니다.

**Choose Install Location** — 이 화면이 중요합니다.
기본 경로에는 윈도우 사용자 이름이 들어가는데, 이름이 한글이면 나중에 문제가 생깁니다.
경로 전체를 지우고 아래 경로를 입력하세요.

```
C:\Users\Public\miniforge3
```

`C:\miniforge3` 처럼 C 드라이브 바로 아래에 넣으면 권한 오류가 나니 위 경로를 쓰세요.

**Advanced Installation Options** — 기본값이 이미 우리가 원하는 상태입니다.
*Add installation to my PATH* 와 *Register Miniforge3 as my default Python* 은
**체크하지 않은 채로** 두고 Install 을 누르세요.

PATH 를 체크하지 않는 것은 의도한 것입니다. 그래도 `conda` 는 잘 작동합니다.
설치가 끝나면 시작 메뉴에 **Miniforge Prompt** 가 생기는데, 그 창이 알아서
필요한 설정을 잡아 줍니다. PATH 에 등록하면 오히려 기존에 깔린 아나콘다나
파이썬과 충돌합니다.

### 맥 / 리눅스

받은 파일을 실행합니다.

- 맥에서 `.pkg` 파일을 받았다면 더블클릭하고 안내대로 진행하면 됩니다. **경로는 기본값 그대로** 두세요.
- `.sh` 파일을 받았다면 터미널에서 아래처럼 실행합니다.

```
bash Miniforge3-MacOSX-arm64.sh      # 받은 파일 이름으로 바꿔서
```

라이선스에 동의하고, 설치 위치는 엔터로 기본값을 그대로 받아들이고,
마지막에 `conda init` 을 실행할지 물으면 **yes** 라고 답하세요.
그다음 터미널을 닫고 새로 여세요.

---

## 2. 실습 자료 내려받기

이 페이지 위쪽 초록색 **Code** 버튼 → **Download ZIP** → 압축을 풉니다.

압축은 반드시 풀어서 쓰세요. 압축 파일을 더블클릭해서 열린 창 안에서 실행하면 안 됩니다.

---

## 3. 실습 환경 만들기

먼저 터미널을 엽니다.

- **윈도우** — 윈도우 키를 누르고 `miniforge` 를 입력해서 **Miniforge Prompt** 를 실행합니다.
  (일반 명령 프롬프트가 아닙니다.) 줄 맨 앞에 `(base)` 가 보이면 제대로 열린 것입니다.
- **맥 / 리눅스** — 터미널을 엽니다.

압축을 푼 폴더로 이동합니다.

```
cd Downloads/climstat-2026
```

경로를 직접 치기 번거로우면 `cd ` 까지만 입력하고 **폴더를 터미널 창 안으로 끌어다 놓으면**
경로가 자동으로 채워집니다. 제대로 왔는지는 `dir`(윈도우) 또는 `ls` 로 확인하세요.
`.lock` 파일들이 보이면 맞습니다.

이제 자기 운영체제에 맞는 lock 파일로 환경을 만듭니다.

```
conda create -n climstat --file conda-win-64.lock        # 윈도우
conda create -n climstat --file conda-osx-arm64.lock     # 맥, 애플 실리콘
conda create -n climstat --file conda-osx-64.lock        # 맥, 인텔
conda create -n climstat --file conda-linux-64.lock      # 리눅스 / 우분투
```

lock 파일에는 필요한 패키지와 그 버전이 하나도 빠짐없이 적혀 있습니다.
그래서 수강생 전원이 완전히 동일한 환경을 갖게 됩니다.

---

## 4. JupyterLab 실행

```
conda activate climstat
jupyter-lab
```

브라우저가 자동으로 열립니다.

두 번째 수업부터는 아래 세 줄이면 됩니다.

```
conda activate climstat
cd Downloads/climstat-2026
jupyter-lab
```

---

## 5. 환경 확인

**`00_setup_check.ipynb`** 를 열고 위에서부터 **모든 셀을 순서대로** 실행하세요.

각 셀은 확인 번호를 함께 출력합니다. 전부 통과했든 중간에 오류가 났든,
다 끝나면 **노트북을 저장(Ctrl+S)하고 그 `.ipynb` 파일 자체를 제출**해 주세요.
오류 메시지가 파일 안에 그대로 저장되기 때문에, 화면 캡처보다 훨씬 도움이 됩니다.

커널 이름은 `Python 3 (ipykernel)` 로 표시됩니다. 정상입니다.
`climstat` 환경에서 JupyterLab 을 실행했다면 그게 곧 climstat 커널입니다.

---

## 문제가 생기면

언제든 처음부터 다시 만들 수 있습니다. 아래 두 줄이면 환경을 지우고 lock 파일에서
다시 만듭니다. 노트북이나 자료는 건드리지 않습니다.

```
conda env remove -n climstat
conda create -n climstat --file conda-win-64.lock
```

| 오류 메시지 | 원인 |
|---|---|
| `conda is not recognized` | 윈도우에서 일반 명령 프롬프트를 쓴 경우입니다. Miniforge Prompt 로 여세요. |
| `No such file or directory: conda-win-64.lock` | 폴더를 잘못 찾아왔습니다. `dir` 또는 `ls` 로 확인하세요. |
| `ModuleNotFoundError` | 환경이 활성화되지 않았습니다. `conda activate climstat` 을 먼저 실행하세요. |
| 지도에 해안선이 안 나옴 | 환경이 온전하지 않습니다. 위 두 줄로 다시 만드세요. |

실습에 필요한 패키지는 모두 들어 있습니다. 개인적으로 다른 패키지를 써 보고 싶다면
`pip install` 대신 `conda install -c conda-forge 패키지이름` 을 쓰세요.
conda 환경 안에서 pip 을 섞어 쓰면 환경이 조용히 깨지는 경우가 있습니다.
그러다 문제가 생겨도 위 두 줄로 다시 만들면 되니 부담 갖지 마세요.

---

## 이 저장소에 들어 있는 것

| 파일 | 용도 |
|---|---|
| `conda-*.lock` | 운영체제별 패키지 목록 (버전까지 고정) |
| `environment.yml` | lock 파일을 만들 때 쓴 패키지 목록 |
| `00_setup_check.ipynb` | 환경이 제대로 만들어졌는지 확인하는 노트북 |
| `waveletFunctions.py` | 수업 후반에 사용할 시계열 분석 함수 파일 |
| `data/` | 환경 확인용 샘플 자료 |
