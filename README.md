# 전국 경찰 순찰 안전지도 — 정적 웹 (권역 분할 배포판)

`web/` 폴더 전체를 GitHub Pages 루트로 배포한다.

## 구성

- `index.html` — 권역 선택 + 사업 개요
- `method.html` — 방법론
- `sudogwon/ gangwon/ chungcheong/ honam/ yeongnam/ jeju/` — 권역별 안전지도 (자체 타일·포인트 자산 포함)

안전지수는 전국 공통 산식으로 산출되며, 권역은 표시·배포 단위다.

## 카카오 JS 키

빌드 시 `KAKAO_JS_KEY`가 있으면 난독화 내장된다. 카카오 콘솔에서
플랫폼 Web 사이트 도메인 등록(`http://localhost:8000`, `https://<계정>.github.io`)과
제품 설정 > 카카오맵 사용 ON 이 필요하다.

## 로컬 확인

```bash
cd web && python3 -m http.server 8000
```

`file://` 직접 열기 금지(fetch CORS 차단).

## 재생성

```bash
KAKAO_JS_KEY="JS키" python3 data/scripts/build_web.py
```
