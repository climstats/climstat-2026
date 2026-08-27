# 리눅스 / 우분투 — 실습 환경 설치

[← 저장소 첫 화면으로](https://github.com/climstats/climstat-2026/tree/main)

---

## 1. Miniforge 설치

**[conda-forge.org/download](https://conda-forge.org/download/)** 에 접속해서
**Linux — `x86_64 (amd64)`** 를 받습니다.
다운로드 폴더를 연 후 터미널을 실행하고(Ctrl+Alt+T) 터미널에서 받은 파일을 실행합니다.

```
bash Miniforge3-Linux-x86_64.sh
```
<img width="962" height="730" alt="스크린샷, 2026-08-27 12-16-18" src="https://github.com/user-attachments/assets/82dc3cf0-c800-452a-aa98-234c91e875d0" />


라이선스는 아래 방향키로 넘긴 뒤 `yes`를 입력하고,

<img width="965" height="721" alt="스크린샷, 2026-08-27 12-17-20" src="https://github.com/user-attachments/assets/bcfa44b9-1261-4d8a-999c-78f79334f884" />


설치 위치를 물으면 엔터를 입력하세요

<img width="774" height="540" alt="스크린샷, 2026-08-27 12-18-00" src="https://github.com/user-attachments/assets/8d775958-5644-4886-984c-00e4efa2306c" />


마지막에 `conda init` 을 실행할지 물으면 **`yes`** 를 입력하세요 

<img width="743" height="509" alt="스크린샷, 2026-08-27 12-18-52" src="https://github.com/user-attachments/assets/d89b0048-23b2-47d5-b62a-43b0b2a7fc94" />

완료된 화면을 확인한 후 

<img width="737" height="498" alt="스크린샷, 2026-08-27 12-19-39" src="https://github.com/user-attachments/assets/1cc8d48f-ce88-40a6-96f7-df8b2d5792b0" />

터미널을 재실행하면 맨 앞에 `(base)` 가 보입니다.

<img width="773" height="542" alt="스크린샷, 2026-08-27 12-20-49" src="https://github.com/user-attachments/assets/8d3d2486-4cf7-44ac-bbae-438bb8341b71" />

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
