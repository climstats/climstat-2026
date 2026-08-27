# 리눅스 / 우분투 — 실습 환경 설치

[← 저장소 첫 화면으로](https://github.com/climstats/climstat-2026/tree/main)

---

## 1. Miniforge 설치

**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서
**Linux — `x86_64 (amd64)`** 를 받습니다.

터미널에서 받은 파일을 실행합니다.

```
bash Miniforge3-Linux-x86_64.sh
```

라이선스는 아래 방향키로 넘긴 뒤 `yes`, 설치 위치는 엔터로 기본값을 그대로 받고,
마지막에 `conda init` 을 실행할지 물으면 **`yes`** 라고 답하세요.

그다음 터미널을 닫고 새로 열면 줄 맨 앞에 `(base)` 가 보입니다.

---

## 2. 실습 자료 내려받기

저장소 첫 화면 위쪽의 초록색 **Code** 버튼 → **Download ZIP** → 압축을 풉니다.

---

## 3. 실습 환경 만들기

압축을 푼 폴더로 이동한 뒤 환경을 만듭니다.

```
cd ~/Desktop/climstat-2026-main
conda create -n climstat --file env/conda-linux-64.lock
```

`ls` 로 `.lock` 파일들이 보이는지 먼저 확인하세요.

---

## 4. JupyterLab 실행

```
conda activate climstat
jupyter-lab
```

---

설치가 끝났으면 [저장소 첫 화면](https://github.com/climstats/climstat-2026/tree/main)의 **환경 확인** 으로 돌아가 주세요.
