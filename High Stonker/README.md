# High Stonkers — 웹 빌드

이 폴더를 GitHub Pages에 올리면 브라우저에서 게임이 실행됩니다.

## 로컬에서 확인

```bash
cd web
python -m http.server 8080
```

브라우저에서 http://localhost:8080 을 엽니다. (`file://`로 열면 동작하지 않습니다.)

첫 접속 시 COOP/COEP 헤더용 서비스워커 때문에 **한 번 새로고침**될 수 있습니다.

## GitHub Pages에 올리기

1. 저장소 루트에 `index.html`이 있으면 Pages가 README 대신 그쪽으로 갑니다.
2. 루트 `index.html`은 자동으로 이 `web/` 폴더로 이동합니다.
3. GitHub → **Settings → Pages**
   - Source: Deploy from a branch
   - Branch: `main` (또는 사용 중 브랜치)
   - Folder: `/ (root)`
4. 배포 후 `https://<username>.github.io/<repo>/` 접속 → 게임 실행

## 게임 다시 패키징

소스를 수정한 뒤 `.love`만 다시 만들려면:

```powershell
powershell -File tools/build-web.ps1
```

love.js 런타임(`player.js`, `11.5/`, `lua/` 등)은 이미 포함되어 있습니다.
