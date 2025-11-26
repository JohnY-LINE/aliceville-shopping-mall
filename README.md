# 🏢 Aliceville Shopping Mall

**린스트라우스 앨리스빌 상가** 공식 웹사이트

> 현대적이고 감각적인 쇼핑몰 웹사이트 - React + Tailwind CSS + Supabase

[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue)](https://github.com/JohnY-LINE/aliceville-shopping-mall)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Vercel](https://img.shields.io/badge/Deployed-Vercel-black)](https://aliceville-shopping-mall.vercel.app)

---

## 📋 프로젝트 소개

Aliceville는 **300+ 프리미엄 매장**을 한곳에서 경험할 수 있는 쇼핑몰 웹사이트입니다.

### 🎯 주요 기능

- ✅ **6개 카테고리** - 패션, 카페, 뷰티, 식당, 라이프, 키즈
- ✅ **36개 매장** - 실제 이미지 및 상세 정보
- ✅ **종합 관리자 시스템** - 매장, 브랜드, 이벤트, 커뮤니티 관리
- ✅ **진열 관리 시스템** - AI 기반 스마트 추천
- ✅ **다국어 지원** - 한국어, 영어, 일본어
- ✅ **반응형 디자인** - 모바일 최적화

---

## 🚀 빠른 시작

### 🎯 지금 바로 시작하기

1. **GitHub 업로드** - [GITHUB_UPLOAD_GUIDE.md](./GITHUB_UPLOAD_GUIDE.md)
2. **Supabase 설정** - [SUPABASE_SETUP_GUIDE.md](./SUPABASE_SETUP_GUIDE.md)
3. **배포** - [DEPLOYMENT_GUIDE.md](./DEPLOYMENT_GUIDE.md)

**📘 상세 가이드:** [QUICK_START.md](./QUICK_START.md)

---

## 🚀 기술 스택

### Frontend
- **React 18** - 최신 React 기능
- **TypeScript** - 타입 안전성
- **Tailwind CSS v4.0** - 최신 유틸리티 CSS
- **Vite** - 빠른 빌드 도구

### Backend (Supabase)
- **PostgreSQL** - 데이터베이스
- **Supabase Auth** - 인증 시스템
- **Supabase Storage** - 이미지 저장소
- **Row Level Security** - 보안

### UI Libraries
- **ShadCN UI** - 40+ 컴포넌트
- **Lucide React** - 아이콘
- **Recharts** - 차트
- **Sonner** - 토스트 알림

---

## 📦 설치 및 실행

### 1. 프로젝트 클론

```bash
git clone https://github.com/JohnY-LINE/aliceville-shopping-mall.git
cd aliceville-shopping-mall
```

### 2. 의존성 설치

```bash
npm install
```

### 3. 환경 변수 설정

`.env` 파일을 생성하고 Supabase 정보를 입력하세요:

```env
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### 4. 개발 서버 실행

```bash
npm run dev
```

브라우저에서 `http://localhost:5173` 접속

### 5. 프로덕션 빌드

```bash
npm run build
npm run preview
```

---

## 🗄️ Supabase 설정

### 1. Supabase 프로젝트 생성

1. [Supabase](https://supabase.com) 접속
2. 새 프로젝트 생성
3. 데이터베이스 비밀번호 설정

### 2. 데이터베이스 스키마 생성

`/supabase/schema.sql` 파일을 Supabase SQL Editor에서 실행:

```sql
-- 매장 테이블
CREATE TABLE stores (...);

-- 브랜드 테이블
CREATE TABLE brands (...);

-- 상품 테이블
CREATE TABLE products (...);

-- 이벤트 테이블
CREATE TABLE events (...);

-- 커뮤니티 테이블
CREATE TABLE community_posts (...);

-- Q&A 테이블
CREATE TABLE qna_items (...);

-- Contact 테이블
CREATE TABLE contact_inquiries (...);
```

### 3. Row Level Security (RLS) 설정

보안을 위해 RLS 정책을 설정합니다. 자세한 내용은 `/supabase/policies.sql` 참조

### 4. Storage 버킷 생성

이미지 업로드를 위한 Storage 버킷:
- `store-images`
- `brand-images`
- `product-images`
- `event-images`

---

## 📁 프로젝트 구조

```
aliceville-shopping-mall/
├── components/              # React 컴포넌트
│   ├── HomePage.tsx
│   ├── CategoryPage.tsx
│   ├── StoresPage.tsx
│   ├── AdminPage.tsx
│   ├── admin/              # 관리자 컴포넌트
│   │   ├── DisplayManagementEnhanced.tsx
│   │   ├── BrandsManagement.tsx
│   │   └── ...
│   └── ui/                 # ShadCN UI 컴포넌트
├── contexts/               # React Context
│   ├── LanguageContext.tsx
│   ├── SettingsContext.tsx
│   └── DisplayContext.tsx
├── data/                   # 데이터 파일 (로컬 개발용)
│   ├── storesData.ts
│   ├── brandsData.ts
│   └── ...
├── translations/           # 다국어 번역
├── utils/                  # 유틸리티 함수
├── supabase/              # Supabase 설정
│   ├── schema.sql
│   ├── policies.sql
│   ├── seed.sql
│   └── client.ts
├── styles/                # 스타일
│   └── globals.css
└── App.tsx                # 메인 앱
```

---

## 👨‍💼 관리자 시스템

### 로그인 정보

- **URL**: `/admin-login`
- **아이디**: `admin`
- **비밀번호**: `aliceville2024`

### 관리 기능

1. **매장 관리** - 등록/수정/삭제
2. **브랜드 관리** - 브랜드 관리
3. **신상품 관리** - 상품 관리
4. **이벤트 관리** - 이벤트 생성
5. **이벤트 신청 관리** - 신청 내역
6. **커뮤니티 관리** - 게시글 관리
7. **Q&A 관리** - 문의 답변
8. **Contact 관리** - 문의 처리
9. **진열 관리** - AI 기반 스마트 진열

---

## 🎨 디자인 시스템

### 브랜드 컬러

- **핑크**: `#FF1B6D` - 메인 컬러
- **라벤더**: `#B794F6` - 서브 컬러
- **민트**: `#7FE9C3` - 액센트
- **스카이**: `#5DCCF5` - 액센트
- **코랄**: `#FF5757` - 액센트

### 폰트

- **한글**: Noto Sans KR
- **영문**: Pretendard

---

## 🌍 다국어 지원

현재 지원 언어:
- 🇰🇷 한국어 (기본)
- 🇺🇸 English
- 🇯🇵 日本語

번역 추가: `/translations/translations.ts` 편집

---

## 📞 연락처

- **주소**: 인천 서구 서곶로 45, 린스트라우스 앨리스빌상가
- **이메일**: lu1aliceville2@gmail.com
- **영업시간**: 10:00-14:00

---

## 🔧 개발 환경

### Figma Make에서 개발 시

현재 이 프로젝트는 Figma Make 환경에서 개발되었습니다.

**주의사항:**
1. 모든 import는 상대 경로 사용
2. 이미지는 `ImageWithFallback` 컴포넌트 사용
3. 라이브러리 버전 지정 주의 (`react-hook-form@7.55.0`, `sonner@2.0.3`)

### 로컬 환경으로 마이그레이션

1. `package.json` 의존성 설치
2. Vite 설정 추가 (`vite.config.ts`)
3. TypeScript 설정 추가 (`tsconfig.json`)
4. Tailwind 설정 추가 (`tailwind.config.js`)

자세한 내용은 `/MIGRATION_GUIDE.md` 참조

---

## 📝 라이선스

MIT License

---

## 🎉 기여

기여는 언제나 환영합니다!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📚 문서

- [Figma Make 가이드](/FIGMA_MAKE_GUIDE.md)
- [Supabase 설정 가이드](/SUPABASE_SETUP_GUIDE.md)
- [배포 가이드](/DEPLOYMENT_GUIDE.md)
- [API 문서](/API_DOCUMENTATION.md)

---

**Made with ❤️ by Aliceville Team**