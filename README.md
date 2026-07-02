# m7 Audio Review — 트랙별 오디오 리뷰 웹데모

50개 클립의 m7(SED-지배 + Qwen 리뷰) description으로 Unified-ConRet(nc30) 생성한 오디오를
트랙별로 청취하고, 각 트랙에 **실시간 공유 코멘트**를 다는 리뷰 페이지.

## 🔗 열기
- **https://doeunjeong.github.io/m7-audio-review/**
- 클립 클릭 → final_mix 재생(영상+타임라인 동기) · 트랙별 최종/원본(편집전) 오디오 · ref✓/no-ref 배지

## 💬 실시간 공유 코멘트 (giscus = GitHub Discussions)
- 각 트랙 아래 **`공유 코멘트 열기`** → 그 트랙 전용 스레드가 열림(트랙별 분리, mapping=specific)
- 작성하려면 **GitHub 로그인** 필요. 게시하면 모두가 같은 스레드에서 즉시 확인
- 코멘트는 이 repo의 **Discussions**(General 카테고리)에 영구 저장

### ⚙️ 최초 1회 필수 설정 (repo 소유자 = DoeunJeong)
> 이걸 안 하면 코멘트 창은 떠도 저장이 안 됩니다.
1. **giscus 앱 설치**: https://github.com/apps/giscus → *Install* → **DoeunJeong/m7-audio-review** 선택
2. Discussions 활성화(이미 켬) + General 카테고리(이미 사용) — 추가 작업 없음

## 재배포 (내용 갱신 시)
```bash
cd <이 폴더>
python3 /home/judejiwoo/VideoDescriptionEx/build_webdemo.py --root "$PWD" \
  --giscus-repo DoeunJeong/m7-audio-review --giscus-repo-id R_kgDOTL1ZDg \
  --giscus-category General --giscus-category-id DIC_kwDOTL1ZDs4DAYEE
git add webdemo/ && git commit -m "update webdemo"
# push: 이 서버엔 JudeJiwoo 자격증명 캐시가 남아 일반 push가 403 → inline 토큰 사용:
git push "https://DoeunJeong:$(GH_CONFIG_DIR=$PWD/.gh gh auth token)@github.com/DoeunJeong/m7-audio-review.git" main:main
```

## ⚠️ 공개 범위
- Free 플랜 제약으로 **public repo + Pages** 상태 → 영상·오디오가 URL로 공개 다운로드 가능.
- 리뷰 종료 시 비공개 전환: `gh api -X PATCH repos/DoeunJeong/m7-audio-review -F private=false`
  (단 private 전환 시 Free 플랜은 Pages가 내려가 URL이 죽습니다.)
