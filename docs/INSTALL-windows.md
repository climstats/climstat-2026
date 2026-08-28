# 윈도우 — 실습 환경 설치

[← 저장소 첫 화면으로](https://github.com/climstats/climstat-2026/tree/main)

> **이미 아나콘다가 설치되어 있다면** 1번을 건너뛰고
> **[2. 실습 자료 내려받기](#2-실습-자료-내려받기)** 부터 진행하세요.
> Miniforge Prompt 대신 **Anaconda Prompt** 를 사용하면 됩니다.
> 오류가 나면 그때 미니포지를 설치하세요.

---

## 1. Miniforge 설치

Miniforge는 파이썬 패키지를 관리해 주는 `conda`를 설치하는 작은 프로그램입니다.

**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서
**Windows — `x86_64`** 를 받으세요.

받은 `.exe` 파일을 실행합니다. *Welcome* 과 *License Agreement* 는 그대로 넘어가고,
다음 세 화면만 주의해 주세요.

### Select Installation Type

**Just Me** 를 그대로 둡니다.

<img width="628" height="488" alt="캡처3" src="https://github.com/user-attachments/assets/374672e0-655b-4fb8-a672-ddadd398873b" />

### Choose Install Location

이 화면이 중요합니다. 기본 경로에는 윈도우 사용자 이름이 들어가는데,
이름이 한글이면 나중에 경로 문제가 생길 수 있습니다.
경로 전체를 지우고 아래 경로를 입력하세요.

```
C:\Users\Public\miniforge3
```

<img width="615" height="486" alt="캡처" src="https://github.com/user-attachments/assets/3b243436-e1dc-4544-98b7-cb38feedb60d" />

### Advanced Installation Options

**첫 번째와 네 번째만 체크**된 상태로 두고 Install 을 누르세요.

<img width="626" height="486" alt="캡처2" src="https://github.com/user-attachments/assets/fa34d3f0-4e0c-4fba-9658-c655a34c755d" />

첫 번째(Create shortcuts)를 빠뜨리면 **Miniforge Prompt** 가 생기지 않아
다음 단계로 넘어갈 수 없으니 꼭 확인하세요.

PATH 를 체크하지 않는 것은 의도한 것입니다. 그래도 `conda` 는 잘 작동합니다.
설치가 끝나면 시작 메뉴에 Miniforge Prompt 가 생기는데, 그 창이 알아서 필요한
설정을 잡아 줍니다. PATH 에 등록하면 오히려 기존에 깔린 아나콘다나 파이썬과
충돌합니다.

---

## 2. 실습 자료 내려받기

저장소 첫 화면 위쪽의 초록색 **Code** 버튼 → **Download ZIP** → 압축을 풉니다.

압축은 반드시 풀어서 쓰세요. 압축 파일을 더블클릭해서 열린 창 안에서 실행하면 안 됩니다.

압축을 푼 폴더는 **바탕화면으로 옮겨 주세요.**

---

## 3. 실습 환경 만들기

윈도우 키를 누르고 `miniforge` 를 입력해서 **Miniforge Prompt** 를 실행합니다.
(아나콘다를 쓰는 경우 **Anaconda Prompt**) 
(일반 명령 프롬프트가 아닙니다.)
줄 맨 앞에 `(base)` 가 보이면 제대로 열린 것입니다.


이제 실습 폴더로 이동합니다. 경로를 직접 입력하는 대신 아래 방법을 쓸 수 있습니다.

1. `cd ` 를 입력합니다. (`cd` 뒤에 **한 칸 띄우기**)
2. 바탕화면의 실습 폴더를 **터미널 창 안으로 끌어다 놓습니다.** 경로가 자동으로 채워집니다.
3. 엔터를 누릅니다.

혹은 실습 폴더가 있는 경로를 직접 입력해도 됩니다.

```
cd C:\Users\사용자명\Desktop\climstat-2026-main
```

제대로 왔는지는 `dir` 로 확인하세요. `env`, `notebooks`, `data` 폴더가 보이면 맞습니다.

<img width="1224" height="638" alt="다운로드폴더로" src="https://github.com/user-attachments/assets/660c770c-392f-4ea0-a567-a8e0c29c1586" />

이제 환경을 만듭니다.

```
conda create -n climstat --file env/conda-win-64.lock
```

lock 파일에는 필요한 패키지와 그 버전이 하나도 빠짐없이 적혀 있어서,
수강생 전원이 완전히 동일한 환경을 갖게 됩니다.

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

1. **Miniforge Prompt** 를 엽니다.
2. 위와 같은 방법으로 실습 폴더로 이동합니다. (`cd ` 입력 → 폴더 드래그 → 엔터)
3. `conda activate climstat` 과 `jupyter-lab` 을 실행합니다.

---

설치가 끝났으면 [저장소 첫 화면](https://github.com/climstats/climstat-2026/tree/main)의 **환경 확인** 으로 돌아가 주세요.
