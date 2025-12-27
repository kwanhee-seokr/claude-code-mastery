# Git Workflow 규칙

## 브랜치 전략

### 브랜치 네이밍 규칙
- `feature/기능명`: 새로운 기능 개발
- `fix/버그명`: 버그 수정
- `docs/문서명`: 문서 작업
- `refactor/대상`: 리팩토링
- `test/테스트명`: 테스트 추가/수정

### 기본 워크플로우

```bash
# 1. 새 브랜치 생성 및 이동
git checkout -b feature/기능명

# 2. 작업 수행 후 변경사항 확인
git status

# 3. 변경사항 스테이징
git add .

# 4. 커밋 (의미있는 메시지 작성)
git commit -m "기능: 기능에 대한 설명"

# 5. 원격 저장소에 푸시
git push origin feature/기능명
```

## 커밋 메시지 규칙

### 형식
```
타입: 간단한 설명

상세 설명 (선택사항)
```

### 타입 종류
- `기능`: 새로운 기능 추가
- `수정`: 버그 수정
- `문서`: 문서 수정
- `스타일`: 코드 포맷팅, 세미콜론 누락 등
- `리팩토링`: 코드 리팩토링
- `테스트`: 테스트 코드 추가/수정
- `빌드`: 빌드 관련 파일 수정
- `성능`: 성능 개선

### 예시
```bash
git commit -m "기능: 사용자 로그인 기능 추가"
git commit -m "수정: 회원가입 시 유효성 검사 오류 해결"
git commit -m "문서: README에 설치 가이드 추가"
```

## 주요 명령어

### 상태 확인
```bash
git status                    # 현재 상태 확인
git log --oneline            # 커밋 히스토리 확인
git diff                     # 변경사항 확인
```

### 브랜치 관리
```bash
git branch                   # 로컬 브랜치 목록
git branch -a                # 모든 브랜치 목록
git checkout main            # 브랜치 이동
git branch -d feature/기능명  # 브랜치 삭제
```

### 동기화
```bash
git pull origin main         # 원격 저장소 변경사항 가져오기
git push origin 브랜치명      # 원격 저장소에 푸시
```

### 변경사항 되돌리기
```bash
git reset HEAD 파일명        # 스테이징 취소
git checkout -- 파일명       # 작업 디렉토리 변경사항 취소
git revert 커밋해시          # 커밋 되돌리기 (새 커밋 생성)
```

## 베스트 프랙티스

1. **자주 커밋하기**: 작은 단위로 자주 커밋
2. **의미있는 메시지**: 커밋 메시지는 명확하고 구체적으로
3. **브랜치 사용**: main 브랜치에 직접 커밋하지 않기
4. **동기화 습관**: 작업 전 `git pull`로 최신 상태 유지
5. **리뷰 후 병합**: Pull Request를 통한 코드 리뷰 진행
6. **커밋 전 확인**: `git status`, `git diff`로 변경사항 확인

## 주의사항

- `.gitignore`에 민감한 정보 파일 추가
- 큰 바이너리 파일은 커밋하지 않기
- 강제 푸시(`git push -f`) 사용 자제
- main/master 브랜치 보호 설정 권장
