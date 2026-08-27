# 기후자료 통계분석 

이 수업의 실습에 필요한 가상환경을 만들기 위한 가이드입니다.

**자기 컴퓨터에 맞는 안내를 따라가 주세요.**

| 내 컴퓨터 | 설치 안내 |
|---|---|
| 윈도우 | **[윈도우 설치 안내](docs/INSTALL-windows.md)** |
| 맥 (M1 / M2 / M3 / M4 / 인텔) | **[맥 설치 안내](docs/INSTALL-mac.md)** |
| 우분투 / 리눅스 | **[리눅스 설치 안내](docs/INSTALL-linux.md)** |

설치가 끝나면 아래 **환경 확인**으로 돌아와 주세요.

**이미 아나콘다가 깔려 있다면 지우지 마세요.** 그대로 두고 진행하면 됩니다.

---

## 환경 확인

`notebooks` 폴더의 **`00_setup_check.ipynb`** 를 열고 위에서부터 **모든 셀을 순서대로** 실행하세요.

각 셀은 확인 번호를 함께 출력합니다. 전부 통과했든 중간에 오류가 났든,
다 끝나면 **노트북을 저장(Ctrl+S)하고 그 `.ipynb` 파일 자체를 제출**해 주세요.
오류 메시지가 파일 안에 그대로 저장되기 때문에, 화면 캡처보다 훨씬 도움이 됩니다.


---

## 문제가 생기면

### 자주 나오는 오류

| 오류 메시지 | 어떻게 하면 되나 |
|---|---|
| `conda is not recognized` | 시작 메뉴에서 **Miniforge Prompt** 를 열었는지 확인하세요. 다른 검은 창에서는 `conda` 가 작동하지 않습니다. |
| `No such file or directory` | 실습 폴더로 이동하지 않았습니다. `cd` 로 폴더에 들어간 뒤 다시 실행하세요. |
| `ModuleNotFoundError` | `conda activate climstat` 을 먼저 실행하세요. 창 맨 앞에 `(climstat)` 이 보여야 합니다. |

### 환경을 지우고 다시 만들고 싶을 경우

아래 두 줄로 환경을 다시 세팅할 수 있습니다. 
노트북이나 자료는 건드리지 않으니 부담 갖지 마세요.

```
conda env remove -n climstat #실습환경 지우기 
conda create -n climstat --file env/conda-운영체제.lock #실습환경 다시 만들기 
```

마지막 줄의 lock 파일 이름은 자기 컴퓨터에 맞는 것으로 실행해주세요.

### climstat 환경에 패키지를 추가로 설치해야 할 경우

실습에 필요한 패키지는 모두 들어 있습니다. 그래도 다른 패키지가 필요하면
반드시 아래처럼 설치하세요.

```
conda activate climstat
conda install -c conda-forge 패키지이름
```

---

## 이 저장소에 들어 있는 것

| 폴더 / 파일 | 용도 |
|---|---|
| `docs/` | 운영체제별 설치 안내 |
| `env/` | 실습 환경 정의 파일 (`environment.yml`, `conda-*.lock`) |
| `notebooks/` | 실습 노트북 (`00_setup_check.ipynb` 등) |
| `data/` | 실습에 쓰는 자료 |
