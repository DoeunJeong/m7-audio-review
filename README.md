# m7 Audio Review — 트랙별 오디오 리뷰 웹데모

50개 클립의 m7(SED-지배 + Qwen 리뷰) description으로 Unified-ConRet(nc30) 생성한 오디오를
트랙별로 청취하고, 각 트랙에 **문제점 코멘트**를 다는 리뷰 페이지.

## 열기
- 배포됨: `webdemo/index.html` (루트 접속 시 자동 이동)
- 클립 클릭 → final_mix 재생(영상+타임라인 동기) · 트랙별 최종/원본(편집전) 오디오 · ref✓/no-ref 배지

## 코멘트 작성 (여러 명)
- 각 트랙 아래 `🐞 문제점 코멘트`에 작성 → **브라우저에 자동 저장**(localStorage)
- 좌측 상단 **리뷰어 이름** 입력 후 `코멘트 내보내기(JSON)` → 파일 공유
- 받은 JSON은 `가져오기`로 로드 → 각 트랙에 `작성자: 내용`으로 함께 표시

## GitHub Pages 배포 (인증 필요 — 아래 실행)
```bash
cd <이 폴더>
gh auth login                       # 1) 인증 (대화형)
gh repo create m7-audio-review --private --source=. --remote=origin --push   # 2) private repo + push
# 3) Pages 활성화: repo Settings → Pages → Source: Deploy from a branch → main / (root)
# → https://<user>.github.io/m7-audio-review/
```
> ⚠️ 표준 플랜에선 private repo라도 Pages **사이트는 공개 URL**로 접근됩니다(미디어 포함).
> 진짜 비공개는 Enterprise만 가능 — 아니면 팀이 repo clone 후 로컬에서 `webdemo/index.html` 열기.
