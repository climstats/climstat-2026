# 맥 — 실습 환경 설치

[← 저장소 첫 화면으로](https://github.com/climstats/climstat-2026/tree/main)

> **이미 아나콘다가 설치되어 있다면** 1번을 건너뛰고
> **[2. 실습 자료 내려받기](#2-실습-자료-내려받기)** 부터 진행하세요.
> 아나콘다에 들어 있는 `conda` 로도 동일하게 환경을 만들 수 있습니다.
> 오류가 나면 그때 미니포지를 설치하시면 됩니다.

---

## 1. Miniforge 설치

Miniforge는 파이썬 패키지를 관리해 주는 `conda`를 설치하는 작은 프로그램입니다.

**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서
자기 맥에 맞는 설치 파일을 받으세요.

| 내 맥 | 받을 파일 |
|---|---|
| M1 / M2 / M3 / M4 칩 | **macOS** — `arm64 (Apple Silicon)` |
| 인텔 칩 | **macOS** — `x86_64 (Intel)` |

어느 쪽인지 모르겠다면 화면 왼쪽 위 사과 메뉴 → **이 Mac에 관하여** →
*칩* 항목을 확인하세요.

받아지는 파일은 `.sh` 로 끝나는 설치 스크립트입니다. 
터미널에서 받은 파일을 실행합니다.

터미널이 어디 있는지 모르겠다면, 화면 오른쪽 위 돋보기(Spotlight)를 누르고
`터미널` 또는 `Terminal` 을 입력하면 됩니다.

```
bash ~/Downloads/Miniforge3-MacOSX-arm64.sh
```

<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 18 09 PM" src="https://github.com/user-attachments/assets/076d3b92-d4ff-415d-aaa5-fa314032fcdb" />




라이선스에 엔터를 입력하시고 

<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 18 26 PM" src="https://github.com/user-attachments/assets/01720d92-7772-412a-b50e-94da6488510e" />


아래 방향키로 넘긴 뒤 `yes`를 입력합니다 , 

<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 18 50 PM" src="https://github.com/user-attachments/assets/7aabe810-da83-4ab2-8ebf-3d075a5cd9d8" />


설치 위치는 엔터를 입력해 기본값을 고정합니다.

<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 19 02 PM" src="https://github.com/user-attachments/assets/4019d042-12d1-4267-8066-520351fd124b" />


마지막에 `conda init` 을 실행할지 물으면 **`yes`** 를 입력하세요 

<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 19 37 PM" src="https://github.com/user-attachments/assets/8778a59f-9a54-4fbb-bda6-2b7cd6bee861" />


그다음 터미널을 닫고 새로 열면 줄 맨 앞에 `(base)` 가 보입니다.
<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 20 40 PM" src="https://github.com/user-attachments/assets/b3533a76-5bac-4af6-9ffe-96e6c232651d" />


---

## 2. 실습 자료 내려받기

저장소 첫 화면 위쪽의 초록색 **Code** 버튼 → **Download ZIP** → 압축을 풉니다.

압축을 푼 폴더는 **바탕화면으로 옮겨 주세요.**

---

## 3. 실습 환경 만들기

터미널을 엽니다. 줄 맨 앞에 `(base)` 가 보여야 합니다.

(아나콘다를 쓰는 경우에도 동일합니다.)

이제 실습 자료 폴더로 이동합니다.

```
cd ~/Desktop/climstat-2026-main
```
<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 23 47 PM" src="https://github.com/user-attachments/assets/853d5639-dd19-46cd-bb4b-9448b6a6e1fa" />

경로를 치기 번거로우면 `cd ` 까지만 입력하고 (`cd` 뒤에 **한 칸 띄우기**)
바탕화면의 실습 폴더를 **터미널 창 안으로 끌어다 놓아도** 됩니다.
경로가 자동으로 채워집니다.

제대로 왔는지는 `ls` 로 확인하세요. `env`, `notebooks`, `data` 폴더가 보이면 맞습니다.

이제 자기 맥에 맞는 lock 파일로 환경을 만듭니다.

```
conda create -n climstat --file env/conda-osx-arm64.lock     # M1 / M2 / M3 / M4
conda create -n climstat --file env/conda-osx-64.lock        # 인텔
```

<img width="1042" height="721" alt="Screenshot 2026-08-28 at 4 24 42 PM" src="https://github.com/user-attachments/assets/6f69d921-b773-4ea6-8cb3-d86d70ec28e3" />


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
2. `cd ~/Desktop/climstat-2026-main` 으로 실습 폴더에 들어갑니다.
3. `conda activate climstat` 과 `jupyter-lab` 을 실행합니다.

---

설치가 끝났으면 [저장소 첫 화면](https://github.com/climstats/climstat-2026/tree/main)의 **환경 확인** 으로 돌아가 주세요.
