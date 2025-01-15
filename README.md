# planter
### 반려 식물 돌봄 매칭 서비스, planter
![플랜터1 (1)](https://github.com/user-attachments/assets/a1b36e90-d912-4d57-bc01-a873f5faf221)

```혹시, 반려 식물에 관심 있으세요?
최근 반려 식물이 떠오르고 있다는 사실 알고 계신가요?  

플랜테리어에 대한 관심이 커지면서 집에서 반려 동물보다 편하게 키울 수 있는  
'반려 식물'에 대한 관심이 1인 가구에서 특히 커지고 있습니다.  
이들에게 반려 식물 돌봄 매칭 서비스를 제공하기 위해 planter는 시작되었습니다.
```
## 앱 소개
<img src="https://user-images.githubusercontent.com/77619905/204073577-96f18b5f-8d23-450c-8ca2-3c2a7be80fb7.png" width="160" height="346"><img src="https://user-images.githubusercontent.com/77619905/203629433-cf2e82ae-31e8-4b39-8559-076ea6dcd81f.png" width="160" height="346"><img src="https://user-images.githubusercontent.com/77619905/204073586-e23a6f2e-75c8-4fdf-94b3-94ba578e19b8.png" width="160" height="346"><img src="https://user-images.githubusercontent.com/77619905/203629439-a4fb828c-4e58-4122-86b1-ba9a97090f3e.png" width="160" height="346"><img src="https://user-images.githubusercontent.com/77619905/203629441-5f0a3d28-06c1-4b60-8199-ae9d12e1cc80.png" width="160" height="346">

```
주변 식물집사와 전문가에게 반려식물을 믿고 맡길 수 있도록 도와주는 반려식물 매칭 케어 플랫폼
```

- Google Play : https://play.google.com/store/apps/details?id=com.planter
- 개발 기간 : 2022.09 - 2022.11
- 팀 구성 : 기획자 1명, 디자이너 1명, FE 2명, BE 1명
- CMC Demo Day 행사 총 10팀 중 4위

<br />

## Tech Stack
 - React Native
 - Typescript
 - Recoil
 - StyleSheet

<br />

## 기능 설명
#### 로그인
```
유저의 아이디, 비밀번호를 입력 받아 서버와의 통신 후 로그인하는 화면
```
#### 매칭 홈
```
매칭이 가능한 식물 집사 및 전문가들의 목록을 보여주는 화면
원하는 카테고리만 볼 수 있도록 필터링 및 거리, 별점 순으로 정렬 가능
```
#### 전문가 상세 정보
```
매칭 홈에서 식물 집사 및 전문가를 클릭하면 넘어오는 화면
전문가의 상세 정보 및 후기를 볼 수 있고, 매칭 요청, 쪽지 보내기, 신고가 가능함
```
#### 매칭 요청
```
맡길 식물 및 케어 옵션, 케어 날짜, 픽업 형태를 설정하고 식물 집사 및 전문가에게 매칭을 요청하는 화면
```
#### 매칭 내역
```
내가 요청했거나 받은 매칭들의 목록을 보여주는 화면
```
#### 리뷰 작성
```
식물 케어가 완료된 후에 해당 식물 집사 및 전문가에 대해 후기를 작성하는 화면
```
#### 쪽지 작성
```
식물 집사 및 전문가와 쪽지를 보내 소통할 수 있는 화면
```
#### 마이페이지
```
유저의 프로필 정보를 보여주고, 자신의 매칭페이지를 관리할 수 있는 화면
```
#### 내 매칭페이지 관리
```
매칭 허용 여부, 사진, 소개글, 케어 서비스 종류, 사진 제공 여부 정보를 입력하여 매칭 탭의 식물 집사 및 전문가 리스트에 노출 여부를 정할 수 있는 화면
```

<br />

## 담당 업무(프론트엔드 개발자)
- `로그인 기능 구현`

<img src="https://github.com/user-attachments/assets/9dffd8e9-53a3-408b-944d-3a288bc1d1cd" width="360" />

  - useRef를 통해 터치로 인한 API 중복 호출 방지하여 이벤트 처리 개선
    - 변화를 감지하면서도 리렌더링을 발생시키지 않는 useRef를 활용하여 불필요한 리렌더링 방지

<br />

-  `내 주변 식물 집사/전문가 피드 구현`

<img src="https://github.com/user-attachments/assets/daa51198-aa4c-44e1-9f93-185dff43f91f" width="360" />

  - FlatList를 사용하여 내 주변 식물 집사/전문가 피드 구현
    - 스크롤 시 필요한 데이터만 불러와 메모리 소비 감소
  - RefreshControl을 이용해 위로 스크롤할 때마다 새로운 피드를 받아오도록 구현하여 사용자 경험 개선

<br />

-  `쪽지 기능 구현`

<img src="https://github.com/user-attachments/assets/3dba6e46-dcbd-4dfd-8152-fced8c308509" width="360" />

  - 이미지를 첨부한 쪽지 작성 및 전송 기능 구현
    - react-native-image-crop-picker를 활용해 이미지 편집 후 FormData로 서버 전송 구현
  - 쪽지 전송 후 페이지 전환 시 쪽지 리스트 미업데이트 현상 발생
    - React Navigation 공식 문서를 통해 웹과 모바일 앱의 화면 전환 방식 차이 파악
    - useEffect를 useFocusEffect로 대체하여 실시간 쪽지 리스트 업데이트 구현

<br />

-  `마이페이지 구현`

<img src="https://github.com/user-attachments/assets/3b86a180-ebb9-4246-9c11-fae08c7cedf9" width="360" />

  - 마이페이지 Tap 구현
    - useNavigate와 useParams를 활용하여 데이터 기반 화면 동적 업데이트
    - URL 매개변수를 통한 즉각적인 화면 업데이트 구현 및 사용자 경험 개선
   
<br />

## 폴더 구조
```
📂src
 ┣ 📂assets
 ┃ ┣ 📂icon
 ┃ ┣ 📂img
 ┃ ┗ 📂illust
 ┣ 📂components
 ┃ ┣ 📂common
 ┃ ┣ 📂ExpertDetail
 ┃ ┣ 📂matching
 ┃ ┣ 📂matchingHistory
 ┃ ┣ 📂matchingRequest
 ┃ ┣ 📂Message
 ┃ ┗ 📂MyPage
 ┣ 📂recoil
 ┃ ┗ 📂atoms
 ┣ 📂screens
 ┃ ┣ 📂ExpertDetail
 ┃ ┣ 📂FindID
 ┃ ┣ 📂FindPW
 ┃ ┣ 📂Login
 ┃ ┣ 📂Matching
 ┃ ┣ 📂MatchingHistory
 ┃ ┣ 📂MatchingRequest
 ┃ ┣ 📂Message
 ┃ ┣ 📂MyPage
 ┃ ┣ 📂Review
 ┃ ┣ 📂Signup
 ┃ ┣ LoginStack.tsx
 ┃ ┣ MainTab.tsx
 ┃ ┣ Navigator.tsx
 ┃ ┗ RootStack.tsx
 ┣ 📂utils
 ┗ App.tsx
 ```
