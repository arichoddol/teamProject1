# 반려동물 용품 쇼핑몰

## 프로젝트 소개
반려 동물을 키우는 가구가 증가하면서 함께 늘어나는 반려 동물 용품 수요를 해결하기 위한 서비스를 제공하는 프론트 기반 팀 프로젝트입니다.

사용자는 다양한 카테고리의 반려 동물 용품에 대한 쇼핑몰 기능과 후기/댓글 등록, 회원 관리(관리자) 등의 기능을 이용할 수 있습니다.
<br>
**📅프로젝트 기간** : 2025.06 - 2025.07 
<br>
<br>
**👥 팀 인원** : 3명 
<br>

---

## 팀 구성 및 역할

<br>
<table>
  <tr>
    <th>정기호(팀장)</th>
    <th><strong>유연준(본인)</strong></th>
    <th>천승우</th>
  </tr>
  <tr>
    <td>메인 페이지<br>로그인 페이지<br>관리자 페이지<br>레이아웃, 라우터 설계<br>Git 관리</td>
    <td><strong>컨테이너 상품 페이지<br>장바구니 시스템<br>상품 JSON DB</strong></td>
    <td>컨테이너 Header<br>컨테이너 Footer<br>상품 페이지<br>댓글, 리뷰 시스템</td>
  </tr>
</table>
<br>

---

## 📁 기술 스택

#### Frontend
- HTML, CSS, JavaScript, React, Redux Toolkit
- Vite, Axios
- Kakaomap API
- JSON

---

## ⭐ 전체 주요 기능

<details>
<summary>👥 1. 회원</summary>
  <br>
  
- 회원가입 <br>
- 로그인 / 로그아웃 <br>
</details>
  <br>

<details>
<summary>🛒 2. 쇼핑몰 기능</summary>
  <br>
  
- 상품 목록 및 상세 조회<br>
- 리뷰 / 댓글 기능
- 장바구니/결제 기능  <br>
- 사용자 결제 내역 조회 <br>
</details>
  <br>

<details>
<summary>🛠 4. 관리자(Admin)</summary>
  <br>
  
- 전체 결제 내역 조회<br>
- 회원 정보 조회<br>
- 쇼핑몰 상품 등록<br>
- 관리자 대시보드 <br>
</details>
  <br>

<details>
<summary>🌐 5. Open API</summary>
  <br>
  
- Kakaomap API<br>
</details>
  <br>
  
---

## 🧑‍💻 담당한 기능
### 📦 1. 상품 페이지

<details>
<summary>상품 목록 컴포넌트</summary>
<br>
<img width="584.5" height="276.5" alt="image" src="https://github.com/user-attachments/assets/88be509c-a109-449b-a768-2e49e3a38e19" />

  - 상품 레이아웃을 두고 상품 카테고리 별로 구분
  <br><br>
  - 상품 데이터를 직접 구성한 JSON DB에서 Axios를 통해 불러와 랜더링
  <br><br>
  - Grid 레이아웃을 사용하여 다양한 기기에서도 보기 편한 반응형 UI 구현
  <br><br>
  - 서브-카테고리/페이지네이션 기능으로 사용자의 편의성 향상
<br><br><br>

  <img width="275.6" height="25.6" alt="image" src="https://github.com/user-attachments/assets/bc368992-1c92-4291-acaf-df2585dc004f" />
<br>

  - isActive()함수로 UI 상태를 관리하여 현재 선택된 카테고리 표시
  <br><br><br>
  <img width="170.4" height="188" alt="image" src="https://github.com/user-attachments/assets/2282947d-87b8-4496-9aab-7429bf9e15b3" />
  <br>
https://github.com/arichoddol/teamProject1/tree/main
 - 상품 상세 페이지로 이동하지 않아도 목록에서 바로 장바구니 추가 가능
</details>
<br>

<details>
<summary>상품 상세 컴포넌트</summary>
<br>
  <img width="504.5" height="351" alt="image" src="https://github.com/user-attachments/assets/3440a1c9-cd64-4d95-a223-4c410ccf284f" />
  <br>
  
 - 이미지 슬라이더로 여러 상품 이미지 제공<br><br>
 - 상품 수량 증감 버튼으로 장바구니에 담을 상품 수량 조정 가능<br><br>
 - 장바구니 추가 시 장바구니 Redux 상태를 업데이트하고 모달창을 이용해 장바구니 페이지로 이동 여부 확인<br><br>
 - 바로 결제 시 결제 페이지로 이동
</details>
<br>

<details>
<summary>레이아웃 구조</summary>
<br>
  <img width="160" height="157" alt="z" src="https://github.com/user-attachments/assets/5dffcdbc-ae03-488e-9cb7-7d434fd4e421" />
<br>
  
  - 담당 상품 페이지에서 공통으로 사용하는 서브-카테고리 / 상품 상세 레이아웃 / 이미지 슬라이더 등을 별도 컴포넌트로 분리
  <br><br>
  - 각 페이지에서 같은 구조와 스타일을 유지하도록 설계
  <br><br>
  - 공통 컴포넌트를 활용하여 재사용이 가능한 구조로 UI 일관성과 유지 보수성 향상
  <br>
</details>
<br>

### 🛒2. 장바구니
<details>
<summary>장바구니 Slice</summary>
<br>
  
  - 장바구니 상태를 <strong>Redux Toolkit</strong>으로 중앙에서 관리 <br><br>
  - 페이지 이동 시에도 Redux 스토어 기반으로 상태 유지<br><br>
  - 장바구니 추가, 삭제, 수량 증가/감소 등 데이터 변경 로직을 Slice 내부에서 통합 관리<br><br>
  - 상품 갯수, 총 금액 계산 등 장바구니 관련 정보를 한 곳에서 처리

  <br>
  <img width="89" height="83" alt="image" src="https://github.com/user-attachments/assets/891d4860-2bb5-4f0c-b448-a98721b7f2e1" />
  <br>

  - Header 장바구니 아이콘에 useSelector로 장바구니 상품 개수 실시간 표시
</details>
<br>

<details>
<summary>장바구니 컴포넌트</summary>
<br>
  <img width="567.5" height="221.5" alt="image" src="https://github.com/user-attachments/assets/0e8ab5de-cfca-4355-b5a6-9997d24e2b8d" />
  <br>

  - 각 상품의 개별 삭제 버튼으로 원하는 상품만 삭제 가능<br><br>
  - 전체 선택 / 개별 선택 기능을 구현하여 선택된 상품 목록을 filter()로 분리해 결제 페이지로 전달하는 구조<br>
</details>
<br>

### 3. 결제
<details>
<summary>결제 Slice</summary>
<br>
  
  - 장바구니 상태를 Redux Toolkit으로 중앙에서 관리 <br><br>
  - 페이지 이동 시에도 상태가 유지되도록 Redux 스토어 기반 구조 적용<br><br>
  - 장바구니 추가, 삭제, 수량 증가/감소 등 주요 로직 Slice 내부에서 처리<br><br>
  - 상품 수, 총 금액 계산 등 장바구니 관련 상태를 한번에 관리
  <br>
</details>
<br>

<details>
<summary>결제 컴포넌트</summary>
<br>
  <br>

  - <br><br>
  - <br>
</details>
<br>

