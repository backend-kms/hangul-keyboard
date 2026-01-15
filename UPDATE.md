# hangul-keyboard Update Log

## 2026.01.15

오늘 수정된 사항:

### 1. Core 기능 개선
- `decompose_hangul_full` 함수 추가
  - 한글 음절을 자모 단위로 분해하여 리스트로 반환
  - 종성이 없는 경우에도 리스트 형태로 반환
  - 비한글 문자는 그대로 포함
- `decompose_hangul_str` 함수 추가
  - `decompose_hangul_full` 결과를 문자열로 합쳐서 반환
  - LLM 입력 및 UI 출력용으로 사용 가능

### 2. README.md 개선
- Features 섹션 업데이트
  - `decompose_hangul_full` / `decompose_hangul_str` 기능 추가
  - 검색 시스템, LLM 전처리, 텍스트 분석에 활용 가능하도록 명시
- Quick Start 섹션 업데이트
  - 예제 코드에 decompose 함수 사용법 추가
  - 문자열과 리스트 형태로 결과 확인 가능

### 3. 테스트 코드 업데이트
- `tests/test_integration.py`에 decompose_hangul 통합 테스트 추가
  - `decompose_hangul_full` 리스트 반환 검증
  - `decompose_hangul_str` 문자열 반환 검증
  - 공백, 숫자, 특수문자, 빈 문자열 등 엣지 케이스 포함
- 기존 `convert_roman_to_hangul` 테스트와 통합하여 로마자 → 한글 → 자모 전체 흐름 검증 가능

### 4. 패키지 구조 유지
- `core.py`와 `mapping.py`에 기능 추가
- 기존 구조 변경 없음, backward compatibility 유지

---