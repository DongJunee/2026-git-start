# 2026-git-start

로컬 컴퓨터에서 추가한 내용입니다.

오늘의 학습 목표 'GitHub와 로컬 저장소의 Merge 충돌 해결 실습'

GitHub 웹에서 추가한 내용입니다.

# 2026 Git Start

오늘의 학습 목표: 작업자 B의 Merge 충돌 실습

오늘의 학습 목표: 작업자 A의 Git 협업 실습

오늘의 학습 목표: 작업자 A·B의 Git 협업 및 Merge 충돌 해결

# Git & GitHub Merge 충돌 해결 실습

## 1. 실습 목표

이번 실습에서는 GitHub의 원격 저장소와 로컬 저장소의 관계를 이해하고,
여러 작업자가 같은 저장소에서 작업할 때 발생할 수 있는
`Merge Conflict`를 직접 발생시키고 해결해본다.

주요 학습 내용

- GitHub 저장소 Clone
- `git add`, `git commit`, `git push`
- `git fetch`
- `git merge`
- `origin/main`과 로컬 `main`의 차이
- Push가 거절되는 이유
- Merge Conflict 발생 원리
- 충돌 해결
- Merge Commit
- 여러 작업자가 GitHub를 이용하여 협업하는 과정


---

# 2. 1단계 - GitHub와 로컬 저장소의 Merge 충돌

## 실습 구조

GitHub 웹과 로컬 컴퓨터에서 같은 `README.md` 파일의
같은 부분을 서로 다르게 수정하여 충돌을 발생시킨다.

```text
GitHub 원격 저장소
        ↕
      Clone
        ↕
로컬 저장소
```

---

## 2-1. GitHub 저장소 Clone

```bash
cd /c

