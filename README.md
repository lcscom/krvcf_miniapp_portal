<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>README.md Downloader</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            height: 100vh; margin: 0; background-color: #f4f6f8;
        }
        .box {
            background: white; padding: 40px; border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.08); text-align: center;
        }
        .btn {
            background-color: #007cbb; color: white; border: none;
            padding: 14px 28px; font-size: 16px; font-weight: bold;
            border-radius: 6px; cursor: pointer; transition: background 0.2s;
            display: inline-flex; align-items: center; gap: 8px;
        }
        .btn:hover { background-color: #005a87; }
    </style>
</head>
<body>

    <div class="box">
        <h2>🚀 KR VCF Mini App Marketplace</h2>
        <p style="color: #666; margin-bottom: 24px;">아래 버튼을 클릭하시면 한/영 다국어 지원 <strong>README.md</strong> 파일이 다운로드됩니다.</p>
        <button class="btn" onclick="downloadReadme()">📥 README.md 다운로드</button>
    </div>

    <script>
        const readmeContent = `# 🚀 KR VCF Mini App Marketplace

사내 클라우드 및 VMware Cloud Foundation(VCF) 인프라 관리를 위한 미니 앱, 스크립트 및 HTML 시뮬레이터를 공유하고 실행할 수 있는 웹 기반 마켓플레이스입니다.

Web-based marketplace for sharing and running mini-apps, scripts, and HTML simulators for enterprise cloud and VMware Cloud Foundation (VCF) infrastructure management.

---

## 🌐 Language Select / 언어 이동
- [한국어 안내](#-한국어-안내-korean)
- [English Guide](#-english-guide)

---

## 🇰🇷 한국어 안내 (Korean)

### ✨ 주요 기능
- **통합 단일 파일 아키텍처 (\`index.html\`)**: 모든 화면 및 관리자 콘솔이 단일 SPA(Single Page Application) 구조로 구현되어 파일 간 데이터 동기화 오차가 전혀 없습니다.
- **실시간 데이터 동기화 & 캐시 우회**: \`apps.json\` 데이터를 GitHub Raw URL 및 \`no-store\` 헤더 기반으로 동적 조회하여 Vercel/CDN 캐시 영향 없이 즉시 반영됩니다.
- **미니 앱 카탈로그 & 데모 룸 분리**:
  - **카탈로그**: 8개 카테고리(\`Compute\`, \`Storage\`, \`Network\`, \`Private AI\`, \`DR\`, \`Dashboard\`, \`Tools\`, \`Code\`)별 외부 웹 링크 분류 및 검색 지원.
  - **데모 룸**: 원클릭 전체화면 HTML 시뮬레이터(iSIM, Raw HTML 등) 모달 구동, \`ESC\` 키 모달 종료, 상단 헤더 실시간 별점(★1~5) 평가 지원.
- **스마트 배지 & 썸네일**:
  - 등록 후 7일 이내 신규 앱 자동 **\`NEW\`** 배지 표시.
  - 썸네일 미지정 시 자동 캡처 또는 브랜드 랜덤 그래디언트 배너 바인딩.
- **앱 신청 및 파일 첨부**:
  - 신청 시 게시 위치(카탈로그 vs 데모 룸) 직접 선택.
  - 대용량 HTML 시뮬레이터 파일(최대 100MB) 업로드 시 **IndexedDB** 내장 보관.
- **통합 관리자 콘솔 (\`#admin\`)**:
  - **SHA-256 이중 보안 인증**: 비밀번호 입력 모달 세션 검증 (\`Dlcjdtn01!\`).
  - **GitHub REST API 커밋 자동화**: 승인/삭제/수정 시 GitHub 저장소의 \`apps.json\` 자동 커밋 & Push.
  - **트래픽 로그 기록**: 접속 유저 IP, 접속 일시, 접속 페이지, User-Agent 모니터링 및 비우기 지원.
  - **통계 초기화 및 백업/복원**: 누적 실행 수/별점 리셋 및 JSON 데이터 Import/Export.

### 📁 프로젝트 구조
\`\`\`text
.
├── index.html        # 통합 웹 애플리케이션 메인 소스
├── apps.json         # 전역 미니 앱 데이터 정의 파일
└── README.md         # 프로젝트 안내 문서
\`\`\`

---

## 🇺🇸 English Guide

### ✨ Key Features
- **Integrated Single Page Architecture (\`index.html\`)**: Single SPA layout containing all workspace views and admin console without cross-file sync latency.
- **Real-Time Data Sync & Cache-Busting**: Dynamic retrieval of \`apps.json\` from GitHub Raw URL using \`no-store\` headers to bypass CDN/Vercel caches.
- **Catalog & Simulator Demo Room**:
  - **Catalog**: Categorized by 8 domains (\`Compute\`, \`Storage\`, \`Network\`, \`Private AI\`, \`DR\`, \`Dashboard\`, \`Tools\`, \`Code\`) with real-time keyword search.
  - **Demo Room**: One-click full-screen modal HTML simulator engine (iSIM, Raw HTML), \`ESC\` key close, and top-bar live rating (★1-5) submission.
- **Smart Badges & Thumbnails**:
  - Automatic **\`NEW\`** pulsing badge for apps registered within 7 days.
  - Auto-generated screenshot or random brand gradient banners for links without explicit thumbnail URLs.
- **App Submission**:
  - Target destination toggle (Catalog vs Demo Room) upon submission.
  - Large HTML simulator file upload support (up to 100MB) backed by browser **IndexedDB**.
- **Admin Console (\`#admin\`)**:
  - **SHA-256 Authentication**: Secure login modal verification (\`Dlcjdtn01!\`).
  - **Automated GitHub Commits**: Direct \`PUT\` requests via GitHub REST API to update \`apps.json\` on repository upon approval/deletion.
  - **Traffic Logging**: Captures public user IP, timestamp, accessed view, and User-Agent strings.
  - **Stats Control & Backup**: Reset view counts/ratings and Export/Import full state JSON data.

---

## ⚠️ Disclaimer / 면책 조항
본 마켓플레이스는 개인/사내 테스트 목적으로 운영되는 비공식 포털입니다. 앱 및 시뮬레이터 사용으로 인해 발생하는 모든 데이터 손실 및 문제의 책임은 사용자 본인에게 있습니다.

This portal is an unofficial marketplace. The user assumes all responsibility for any issues or data loss resulting from the use of these mini-apps.`;

        function downloadReadme() {
            const blob = new Blob([readmeContent], { type: 'text/markdown;charset=utf-8;' });
            const link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.setAttribute('download', 'README.md');
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }
    </script>
</body>
</html>
