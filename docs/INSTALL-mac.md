# 맥 — 실습 환경 설치

[← 저장소 첫 화면으로](https://github.com/climstats/climstat-2026/tree/main)

---

## 1. Miniforge 설치

Miniforge는 파이썬 패키지를 관리해 주는 `conda`를 설치하는 작은 프로그램입니다.

**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서
자기 맥에 맞는 `.pkg` 파일을 받으세요.

| 내 맥 | 받을 파일 |
|---|---|
| M1 / M2 / M3 / M4 칩 | **macOS** — `arm64 (Apple Silicon)` |
| 인텔 칩 | **macOS** — `x86_64 (Intel)` |

어느 쪽인지 모르겠다면 화면 왼쪽 위 사과 메뉴 → **이 Mac에 관하여** →
*칩* 항목을 확인하세요.

받은 `.pkg` 파일을 더블클릭하고 안내대로 **"계속"** 을 눌러 진행하세요.
윈도우와 달리 설치 경로를 따로 정하지 않아도 됩니다.

설치가 끝나면 **터미널을 완전히 닫고 새로 여세요.**
줄 맨 앞에 `(base)` 가 보이면 성공입니다.

터미널이 어디 있는지 모르겠다면, 화면 오른쪽 위 돋보기(Spotlight)를 누르고
`터미널` 또는 `Terminal` 을 입력하면 됩니다.

`(base)` 가 보이지 않는다면 터미널을 껐다 다시 열어 보시고,
그래도 안 되면 조교에게 알려 주세요.

---

## 2. 실습 자료 내려받기

저장소 첫 화면 위쪽의 초록색 **Code** 버튼 → **Download ZIP** → 압축을 풉니다.

압축을 푼 폴더는 **바탕화면으로 옮겨 주세요.**

---

## 3. 실습 환경 만들기

터미널을 엽니다. 줄 맨 앞에 `(base)` 가 보여야 합니다.

이제 실습 폴더로 이동합니다.

```
cd ~/Desktop/climstat-2026
```

경로를 치기 번거로우면 `cd ` 까지만 입력하고 (`cd` 뒤에 **한 칸 띄우기**)
바탕화면의 실습 폴더를 **터미널 창 안으로 끌어다 놓아도** 됩니다.
경로가 자동으로 채워집니다.

제대로 왔는지는 `ls` 로 확인하세요. `env`, `notebooks`, `data` 폴더가 보이면 맞습니다.

이제 자기 맥에 맞는 lock 파일로 환경을 만듭니다.

```
conda create -n climstat --file env/conda-osx-arm64.lock     # M1 / M2 / M3 / M4
conda create -n climstat --file env/conda-osx-64.lock        # 인텔
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

브라우저가 자동으로 열립니다.

두 번째 수업부터는 이렇게 하면 됩니다.

1. 터미널을 엽니다.
2. `cd ~/Desktop/climstat-2026` 으로 실습 폴더에 들어갑니다.
3. `conda activate climstat` 과 `jupyter-lab` 을 실행합니다.

---

설치가 끝났으면 [저장소 첫 화면](https://github.com/climstats/climstat-2026/tree/main)의 **환경 확인** 으로 돌아가 주세요.
