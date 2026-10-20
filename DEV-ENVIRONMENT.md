# DEV-ENVIRONMENT

개발 환경 기록. 2026-10-20에 확인한 결과다. 버전은 각 명령의 출력 그대로 적었다.

## 운영체제와 셸
| 항목 | 값 |
|---|---|
| 운영체제 | Microsoft Windows 11 Pro 10.0.22631 (build 22631) |
| 셸 | PowerShell 7.6.7 (Core) |

## 도구 버전
| 도구 | 명령 | 결과 |
|---|---|---|
| git | `git --version` | `git version 2.56.0.windows.2` |
| node | `node --version` | `v24.22.0` |
| npm | `npm --version` | `11.19.1` |
| uv | `uv --version` | `uv 0.13.1 (62faed335 2026-10-13 x86_64-pc-windows-msvc)` |
| python | `python --version` | 실행되지 않음. 출력 `Python`, 종료 코드 9009 |
| python (backend 가상 환경) | `backend\.venv\Scripts\python.exe --version` | `Python 3.12.15` |

### python 참고
- 터미널의 `python` 명령은 Windows 스토어 연결용 껍데기(`C:\Users\EZ\AppData\Local\Microsoft\WindowsApps\python.exe`)라서 실제 Python이 아니다.
- 실제 Python은 uv가 관리한다. `uv python find`의 결과: `C:\Users\EZ\AppData\Roaming\uv\python\cpython-3.12-windows-x86_64-none\python.exe`
- 백엔드는 `backend/.venv`의 Python 3.12.15를 쓴다.

## 새로 설치한 것
- **시스템 도구**: 이번 기록 작업에서 새로 설치한 것은 없다. 위 도구는 이미 설치되어 있던 것을 확인만 했다.
- **프로젝트 의존성**: M0(커밋 52ef851)에서 추가되어 `package.json`, `pyproject.toml`에 기록된 패키지다. 아래는 설치되어 있는 버전이다.

### frontend (`npm ls --depth=0`)
| 패키지 | 버전 |
|---|---|
| react | 19.3.1 |
| react-dom | 19.3.1 |
| vite | 8.3.4 |
| @vitejs/plugin-react | 6.1.2 |
| oxlint | 1.89.0 |
| @types/react | 19.3.0 |
| @types/react-dom | 19.3.0 |

### backend (`backend/.venv`)
| 패키지 | 버전 |
|---|---|
| fastapi | 0.150.0 |
| uvicorn | 0.54.0 |
| starlette | 1.9.0 |
| pydantic | 2.14.1 |

`pyproject.toml`에 직접 적은 의존성은 `fastapi[standard-no-fastapi-cloud-cli]>=0.150.0` 하나이고, 나머지는 그 의존성으로 함께 설치된 것이다.
