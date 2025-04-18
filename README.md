# 🏔️ 마이킹 - 등산 정보 제공 및 등산 파티 모집 플랫폼

<br/>

## 🗂️ 목차

- [🔎 서비스 소개](#-서비스-소개)
- [👥 팀원 소개](#-팀원-소개)
- [🛠️ 기술 스택](#-기술-스택)
- [✨ 시연 영상](#-시연-영상)
- [💾 DB Schema](#-db-schema)
- [📁 프로젝트 구조](#-프로젝트-구조)

<br/>

## 🔎 서비스 소개

### 주제 선정 배경
1. 흩어진 산 코스 정보 통합 조회 필요  
2. 안전하고 신뢰할 수 있는 등산 메이트 모집 플랫폼 제공

### 서비스 핵심
- 산 정보 조회 및 코스별 상세 정보 제공
- 등산 파티 생성 및 참가 기능
- 사용자 맞춤 파티 필터링
- 관리자 페이지 제공

<br/>

## 👥 팀원 소개

| Name    | Role   | GitHub                                      |
|:-------:|:------:|:--------------------------------------------|
| 권영우   | Team Leader | [kwonup](https://github.com/kwonup)       |
| 고가연   | Team Member | [gayeongogo](https://github.com/gayeongogo) |
| 김민경   | Team Member | [m01310g](https://github.com/m01310g)     |
| 김종윤   | Team Member | [whddbsl](https://github.com/whddbsl)     |

<br/>

## 🛠 기술 스택

### Frontend
- React, Next.js, TypeScript
- Zustand, styled-components
- PWA 지원

### Backend
- Supabase (DB, Storage, Auth)
- SQL Trigger 활용
- Kakao Map API 활용

### 협업 도구
- Figma, Notion, GitHub, Discord

<br/>

## ✨ 시연 영상
[전체 시연 보러가기](https://www.canva.com/design/DAGkb-XsG-o/NozjwFtMg8WaX_Qwu6aaQA/view?utm_content=DAGkb-XsG-o&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=he86a4dea2d)

### 사용자 시스템 - 파티

<p align="center">
  <img src="https://github.com/user-attachments/assets/abc3c9da-0e80-45b3-93ac-d4a70d29a286" width="80%" alt="파티등록" />
  <img src="https://github.com/user-attachments/assets/93a49ed8-38a6-4e38-a50d-d89a6f2d8fc3" width="80%" alt="파티조회" />
  <img src="https://github.com/user-attachments/assets/4d1e05f4-97d0-475b-9a25-9bea0ebbe1cc" width="80%" alt="파티상세조회" />
  <img src="https://github.com/user-attachments/assets/82cb7904-7d46-4534-be74-3ef866ecfb7f" width="80%" alt="파티참가자생성" />
  <img src="https://github.com/user-attachments/assets/39dc49ea-fd01-43c1-91f2-beb218085f6c" width="80%" alt="파티필터링" />
  <img src="https://github.com/user-attachments/assets/cbd51ed4-6c7a-4100-a83f-08fffaf778f6" width="80%" alt="파티삭제" />
</p>

<br/>

## 💾 DB Schema
<p align="center">
  <img src="https://github.com/user-attachments/assets/40ccd9d1-9204-474c-b7e6-c6f8b4de7dba" width="60%" alt="db schema" />
</p>

<br/>

## 📁 프로젝트 구조

### 클린 아키텍처

- UI(Page) [프레젠테이션 계층]: Next.js의 app 디렉터리 내부의 page.tsx 파일들
- API Routes [Adapter 계층]: /app/api 디렉터리 내부의 API 핸들러
- UseCase(Service) [비즈니스 로직 계층]: /application/usecases 디렉터리에서 애플리케이션의 핵심 로직을 처리
- Entity [도메인 계층]: /domain/entities 디렉터리에서 데이터 구조 및 도메인 모델 정의

```
myking
├─ @types
│  └─ next-auth.d.ts
├─ app
│  ├─ (anon)
│  │  ├─ auth
│  │  │  ├─ callback
│  │  │  │  └─ page.tsx
│  │  │  ├─ layout.tsx
│  │  │  ├─ page.styles.ts
│  │  │  ├─ page.tsx
│  │  │  └─ setNickname
│  │  │     ├─ layout.tsx
│  │  │     ├─ page.styles.ts
│  │  │     └─ page.tsx
│  │  ├─ mountains
│  │  │  ├─ page.tsx
│  │  │  └─ [mountainId]
│  │  │     └─ page.tsx
│  │  ├─ myPage
│  │  │  ├─ layout.tsx
│  │  │  ├─ map
│  │  │  │  ├─ page.styles.ts
│  │  │  │  └─ page.tsx
│  │  │  └─ profile
│  │  │     ├─ edit
│  │  │     │  └─ page.tsx
│  │  │     ├─ myCreated
│  │  │     │  ├─ page.styles.ts
│  │  │     │  └─ page.tsx
│  │  │     ├─ myParticipated
│  │  │     │  └─ page.tsx
│  │  │     ├─ page.styles.ts
│  │  │     └─ page.tsx
│  │  ├─ parties
│  │  │  ├─ create
│  │  │  │  ├─ layout.tsx
│  │  │  │  ├─ page.styles.ts
│  │  │  │  └─ page.tsx
│  │  │  ├─ layout.tsx
│  │  │  ├─ page.styles.ts
│  │  │  ├─ page.tsx
│  │  │  └─ [partyId]
│  │  │     ├─ layout.tsx
│  │  │     ├─ page.styles.ts
│  │  │     └─ page.tsx
│  │  └─ search
│  │     └─ page.tsx
│  ├─ admin
│  │  ├─ course
│  │  │  ├─ create
│  │  │  │  ├─ page.styles.ts
│  │  │  │  └─ page.tsx
│  │  │  ├─ page.styles.ts
│  │  │  ├─ page.tsx
│  │  │  └─ [courseId]
│  │  │     └─ edit
│  │  │        ├─ page.styles.ts
│  │  │        └─ page.tsx
│  │  ├─ layout.styles.ts
│  │  ├─ layout.tsx
│  │  ├─ mountain
│  │  │  ├─ create
│  │  │  │  ├─ page.styles.ts
│  │  │  │  └─ page.tsx
│  │  │  ├─ page.styles.ts
│  │  │  ├─ page.tsx
│  │  │  └─ [mountainId]
│  │  │     └─ edit
│  │  │        ├─ page.styles.ts
│  │  │        └─ page.tsx
│  │  ├─ party
│  │  │  ├─ page.styles.ts
│  │  │  └─ page.tsx
│  │  └─ user
│  │     ├─ page.styles.ts
│  │     └─ page.tsx
│  ├─ api
│  │  ├─ admin
│  │  │  ├─ course
│  │  │  │  ├─ create
│  │  │  │  │  └─ route.ts
│  │  │  │  ├─ route.ts
│  │  │  │  └─ [courseId]
│  │  │  │     └─ edit
│  │  │  │        └─ route.ts
│  │  │  ├─ mountain
│  │  │  │  ├─ create
│  │  │  │  │  └─ route.ts
│  │  │  │  ├─ route.ts
│  │  │  │  └─ [mountainId]
│  │  │  │     └─ edit
│  │  │  │        └─ route.ts
│  │  │  ├─ party
│  │  │  │  └─ route.ts
│  │  │  └─ user
│  │  │     └─ route.ts
│  │  ├─ auth
│  │  │  ├─ checkUser
│  │  │  │  └─ route.ts
│  │  │  └─ route.ts
│  │  ├─ mountains
│  │  │  └─ route.ts
│  │  ├─ parties
│  │  │  ├─ create
│  │  │  │  └─ route.ts
│  │  │  ├─ myCreated
│  │  │  │  └─ route.ts
│  │  │  ├─ participated
│  │  │  │  └─ route.ts
│  │  │  ├─ route.ts
│  │  │  └─ [partyId]
│  │  │     └─ route.ts
│  │  ├─ search
│  │  │  └─ route.ts
│  │  └─ user
│  │     ├─ edit
│  │     │  └─ route.ts
│  │     └─ route.ts
│  ├─ layout.tsx
│  ├─ page.styles.ts
│  └─ page.tsx
├─ application
│  ├─ states
│  │  └─ userStore.ts
│  └─ usecases
│     ├─ admin
│     │  ├─ course
│     │  │  ├─ CreateCourseUsecase.ts
│     │  │  ├─ DeleteCourseUsecase.ts
│     │  │  ├─ dto
│     │  │  │  ├─ CourseCreateDto.ts
│     │  │  │  ├─ CourseDetailDto.ts
│     │  │  │  ├─ CourseListDto.ts
│     │  │  │  ├─ CourseUpdateDto.ts
│     │  │  │  └─ MountainListDto.ts
│     │  │  ├─ FindCourseDetailUsecase.ts
│     │  │  ├─ FindCourseUsecase.ts
│     │  │  ├─ FindMountainaByIdUsecase.ts
│     │  │  ├─ FindMountainUsecase.ts
│     │  │  └─ UpdateCourseUsecase.ts
│     │  ├─ mountain
│     │  │  ├─ AdminFindMountainaByIdUsecase.ts
│     │  │  ├─ AdminFindMountainUsecase.ts
│     │  │  ├─ CreateMountainUsecase.ts
│     │  │  ├─ DeleteMountainUsecase.ts
│     │  │  ├─ dto
│     │  │  │  ├─ AdminMountainDto.ts
│     │  │  │  ├─ AdminMountainListDto.ts
│     │  │  │  ├─ MountainCreateDto.ts
│     │  │  │  ├─ MountainDetailDto.ts
│     │  │  │  ├─ MountainListDto.ts
│     │  │  │  └─ MountainUpdateDto.ts
│     │  │  ├─ FindMountainDetailUsecase.ts
│     │  │  ├─ FindMountainUsecase.ts
│     │  │  └─ UpdateMountainUsecase.ts
│     │  ├─ party
│     │  │  ├─ dto
│     │  │  │  └─ PartyListDto.ts
│     │  │  └─ FindPartyUsecase.ts
│     │  └─ user
│     │     ├─ AdminDeleteUserUscases.ts
│     │     ├─ AdminUserListDto.ts
│     │     └─ dto
│     │        └─ AdminFindUserUsecase.ts
│     ├─ mountainDetails
│     │  ├─ dto
│     │  │  ├─ GetMountainDetailsDto.ts
│     │  │  ├─ GetMountainRequestDto.ts
│     │  │  └─ MountainWithCoursesDto.ts
│     │  └─ MountainDetailsUsecase.ts
│     ├─ mountainSearch
│     │  ├─ dto
│     │  │  ├─ SearchMountainDto.ts
│     │  │  └─ SearchMountainRequestDto.ts
│     │  └─ MountainSearchUsecase.ts
│     ├─ party
│     │  ├─ DfPartyCreateUsecase.ts
│     │  └─ dto
│     │     └─ PartyCreateDto.ts
│     ├─ partyLookup
│     │  ├─ dto
│     │  │  ├─ PartyDetailDto.ts
│     │  │  ├─ PartyListDto.ts
│     │  │  ├─ PartyMyCreatedDto.ts
│     │  │  └─ PartyParticipatedDto.ts
│     │  ├─ PartyDetailUsecase.ts
│     │  ├─ PartyListUsecase.ts
│     │  ├─ PartyMyCreatedUsecase.ts
│     │  └─ PartyParticipatedUsecase.ts
│     ├─ PartyMember
│     │  ├─ DfPartyMemberCreateUsecase.ts
│     │  └─ dto
│     │     └─ PartyMemberCreateDto.ts
│     ├─ user
│     │  ├─ CreateUserUsecase.ts
│     │  ├─ dto
│     │  │  ├─ UserCreateDto.ts
│     │  │  ├─ UserDto.ts
│     │  │  └─ UserUpdateDto.ts
│     │  └─ UpdateUserUsecase.ts
│     └─ userLookup
│        ├─ dto
│        │  └─ UserFindDto.ts
│        └─ FindUserUsecase.ts
├─ components
│  ├─ admin
│  │  ├─ sidebar.styles.ts
│  │  └─ Sidebar.tsx
│  ├─ bottomNav
│  │  ├─ bottomNav.styles.ts
│  │  └─ bottomNav.tsx
│  ├─ button
│  │  ├─ submitButton.styles.ts
│  │  └─ submitButton.tsx
│  ├─ header
│  │  ├─ header.style.ts
│  │  └─ header.tsx
│  ├─ party
│  │  └─ filter
│  │     ├─ Filter.styles.ts
│  │     └─ Filter.tsx
│  └─ user
│     ├─ partyButton
│     │  ├─ party.styles.ts
│     │  └─ party.tsx
│     ├─ profileImageUploader
│     │  ├─ ProfileImageUploader.styles.ts
│     │  └─ ProfileImageUploader.tsx
│     ├─ profileNavBar
│     │  ├─ profileNavBar.styles.ts
│     │  └─ profileNavBar.tsx
│     ├─ ProtectedRoutes.tsx
│     └─ userLevel
│        ├─ level.styles.ts
│        └─ level.tsx
├─ context
│  └─ AuthProvider.tsx
├─ domain
│  ├─ entities
│  │  ├─ Course.ts
│  │  ├─ Mountain.ts
│  │  ├─ Party.ts
│  │  ├─ PartyMember.ts
│  │  └─ User.ts
│  └─ repositories
│     ├─ CourseRepository.ts
│     ├─ MountainRepository.ts
│     ├─ PartyMemberRepository.ts
│     ├─ PartyRepository.ts
│     └─ UserRepository.ts
├─ eslint.config.mjs
├─ infrastructure
│  ├─ repositories
│  │  ├─ SbCourseRepository.ts
│  │  ├─ SbMountainRepository.ts
│  │  ├─ SbPartyMemberRepository.ts
│  │  ├─ SbPartyRepository.ts
│  │  └─ SbUserRepository.ts
│  └─ services
│     └─ SupabaseStorageService.ts
├─ next-env.d.ts
├─ next.config.ts
├─ package-lock.json
├─ package.json
├─ public
│  ├─ icons
│  │  └─ app-icon-192x192.png
│  ├─ images
│  │  ├─ back_button.svg
│  │  ├─ home.svg
│  │  ├─ map.png
│  │  ├─ member_default.svg
│  │  ├─ myPage.svg
│  │  ├─ parties.svg
│  │  └─ right_arrow.svg
│  ├─ logos
│  │  └─ logo.png
│  ├─ manifest.json
│  ├─ sw.js
│  └─ workbox-4754cb34.js
├─ README.md
├─ tsconfig.json
├─ tsconfig.tsbuildinfo
└─ utils
   ├─ getToken.ts
   └─ supabase
      └─ server.ts

```
