# POSCO International - 국가별 비자 안내 시스템

인터랙티브 세계지도 기반 비자 정보 허브입니다.

## 🔒 보안 구조

| 항목 | 저장 위치 | GitHub 노출 |
|------|-----------|------------|
| Power Automate Flow URL | 브라우저 localStorage | ❌ 없음 |
| SharePoint 베이스 URL | 브라우저 localStorage | ❌ 없음 |
| 비자 페이지 파일명 매핑 | index.html | ✅ 안전 (내부경로 아님) |
| 국가/좌표 데이터 | index.html | ✅ 공개정보 |

소스코드에는 민감정보가 **전혀 없습니다.**  
API URL 등 설정값은 각 사용자의 브라우저에만 저장됩니다.

---

## ⚙️ 최초 설정 방법

1. `index.html`을 브라우저에서 엽니다.
2. 우측 상단 **⚙️ API 설정** 버튼을 클릭합니다.
3. 아래 두 값을 입력하고 저장합니다:
   - **Power Automate Flow URL** (관리자에게 문의)
   - **SharePoint 베이스 URL** (관리자에게 문의)
4. 설정 후 지도에 비자 데이터가 자동으로 로드됩니다.

> 설정값은 이 기기의 브라우저 localStorage에만 저장됩니다.  
> 다른 기기에서 사용 시 동일하게 재설정이 필요합니다.

---

## 📁 파일 구조

```
visa-hub/
├── index.html          # 메인 페이지 (GitHub 업로드 ✅)
├── config.example.js   # 설정 샘플 (GitHub 업로드 ✅)
├── .gitignore          # config.js 제외 설정
└── README.md           # 이 파일
```

> `config.js` (실제 설정값)는 `.gitignore`에 포함되어 GitHub에 올라가지 않습니다.

---

## 🚀 배포 방법

### GitHub Pages (권장)
1. 이 저장소를 GitHub에 push합니다.
2. Settings → Pages → Branch: main / root 설정
3. 생성된 URL을 팀원에게 공유합니다.
4. 각 팀원이 최초 접속 시 API 설정을 진행합니다.

---

## ⚠️ 주의사항

- Flow URL에는 서명키(`sig=...`)가 포함됩니다. **절대 외부에 공유하지 마세요.**
- localStorage는 브라우저 개발자도구에서 확인 가능합니다. 공용 PC에서는 사용 후 설정을 초기화하세요.
- Flow URL이 변경될 경우 각 사용자가 재설정해야 합니다.
