# 🚀 Introducing the VCF Mini App Marketplace

Hey everyone! 👋

I’ve put together the **VCF Mini App Marketplace** so we can easily find, share, and run all our useful mini-apps and HTML simulators in one centralized place. 

🔗 **Check it out here:** [https://vcfapp.vercel.app/](https://vcfapp.vercel.app/)

I’ll do my best to actively maintain it and follow up on submissions moving forward. If you’ve been experimenting with **"Vibe Coding"** (building tools with AI) and have created any cool scripts or apps, I would be incredibly grateful if you could submit and register them on the portal! 

Let’s build an awesome collection together. Let me know what you think! 🚀

---

## 🛠 Tech Stack & Architecture

This project was built with a lightweight, serverless, and local-first architecture to ensure maximum performance and easy maintenance.

### Frontend
* **HTML5 / CSS3 / Vanilla JavaScript (ES6+)**: Built as a pure Single Page Application (SPA) entirely within a single `index.html` file—no heavy build tools or frameworks required.
* **VMware Clarity UI & Core**: Utilizes `@clr/ui` and `@cds/core` for an enterprise-grade, clean, and responsive design system.
* **Clarity Icons**: Lightweight SVG icon set.

### Storage & State Management
* **IndexedDB**: Used for local browser storage to securely handle and cache large HTML simulator files (up to 100MB) without server overhead.
* **localStorage**: Manages user preferences (Dark/Light theme, EN/KO language) and local access logs.
* **JSONBin.io**: Acts as a lightweight, serverless cloud database for real-time synchronization of the app registry (`apps.json`).

### CI/CD & Infrastructure
* **GitHub REST API**: Integrated directly into the admin console to automatically commit and push state changes (approvals, deletions) to the GitHub repository.
* **Vercel**: Fast and reliable global edge deployment and hosting.
* **Bypass Cache Mechanism**: Utilizes `Blob` URLs and `no-store` fetch policies to bypass CDN caching, ensuring simulators and updates load instantly.


# 🚀 VCF 미니 앱 마켓플레이스 오픈 안내

안녕하세요 여러분! 👋

VCF(VMware Cloud Foundation) 인프라 관리나 업무에 유용하게 쓸 수 있는 미니 앱, 스크립트, HTML 시뮬레이터들을 한곳에서 쉽게 찾아보고 바로 실행할 수 있도록 **VCF 미니 앱 마켓플레이스**를 구축했습니다.

🔗 **마켓플레이스 접속하기:** [https://vcfapp.vercel.app/](https://vcfapp.vercel.app/)

앞으로 제가 최대한 꼼꼼하게 팔로업하며 포털을 유지보수할 예정입니다. 특히, 최근 유행하는 **'바이브 코딩(Vibe Coding, AI를 활용한 코딩)'** 등을 통해 만들어보신 유용한 스크립트나 재밌는 앱이 있다면, 주저하지 말고 포털의 [앱 신청] 탭을 통해 적극적으로 등록해 주시면 정말 감사하겠습니다!

우리만의 유용한 툴 생태계를 함께 만들어 나갔으면 좋겠습니다. 사용해 보시고 언제든 피드백 남겨주세요! 🚀

---

## 🛠 적용된 기술 스택 및 아키텍처 (Tech Stack & Architecture)

이 프로젝트는 유지보수의 편의성과 사용자 퍼포먼스를 극대화하기 위해, 무거운 백엔드 서버 없이 가벼운 **로컬 중심의 서버리스(Serverless) 아키텍처**로 상세하게 설계되었습니다.

### 💻 Frontend (프론트엔드)
* **Vanilla JS & 단일 파일 아키텍처 (SPA):** React나 Vue 같은 무거운 프레임워크나 빌드 도구(Webpack 등) 없이, `index.html` 단일 파일 내에서 모든 라우팅과 뷰 상태를 제어하는 순수 자바스크립트 기반의 SPA로 구현되었습니다.
* **VMware Clarity UI & Core:** 엔터프라이즈 환경에 걸맞은 깔끔하고 직관적인 UI/UX를 제공하기 위해 `@clr/ui` 및 `@cds/core` 웹 컴포넌트 디자인 시스템을 적용했습니다.
* **i18n & Theme:** 로컬 스토리지(`localStorage`)를 활용하여 한국어/영어 즉각 번역 전환 및 다크/라이트 모드를 완벽하게 지원합니다.

### 💾 Storage & Data Management (데이터 및 상태 관리)
* **IndexedDB:** 최대 100MB에 달하는 무거운 HTML 데모 시뮬레이터 파일을 별도의 서버 통신이나 대역폭 낭비 없이 브라우저 내장 로컬 DB에 보관하고 즉시 구동합니다.
* **JSONBin.io 연동:** 별도의 백엔드 서버를 구축하는 대신, 가벼운 서버리스 클라우드 DB를 사용하여 마켓플레이스 앱 목록(`apps.json`) 메타데이터를 실시간으로 동기화합니다.

###  인프라 및 보안 우회 기술 (Infrastructure & CI/CD)
* **GitHub REST API 자동화:** 관리자 콘솔에서 새로운 앱을 승인하거나 삭제할 때, 관리자의 GitHub 토큰을 이용해 GitHub 레포지토리의 `apps.json` 파일을 API로 직접 커밋(Commit)하고 푸시(Push)하도록 구현되어 있습니다.
* **Vercel Edge Hosting:** 글로벌 Edge 네트워크를 통해 빠르고 안정적으로 배포 및 호스팅됩니다.
* **보안 차단 우회 및 Blob 렌더링:** GitHub Raw URL을 `iframe`으로 불러올 때 발생하는 보안 정책(`X-Frame-Options: deny` 등) 차단 문제를 해결하기 위해, `fetch` 로 코드를 먼저 다운로드한 뒤 브라우저 메모리상에서 `Blob URL`로 변환하여 시뮬레이터 모달에 시원하게 렌더링합니다.
* **Cache-Busting (캐시 우회):** Vercel이나 CDN의 강력한 캐싱 정책 때문에 업데이트가 지연되는 것을 막기 위해 `no-store` 헤더와 타임스탬프 쿼리를 결합하여 항상 최신 상태를 유지합니다.
