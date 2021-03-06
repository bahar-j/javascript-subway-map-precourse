# 🚇 지하철 노선도 미션

## 프로젝트 소개

자바스크립트만을 이용해 구현한 미니 지하철 노선 관리 시스템입니다. 역과 노선을 추가(Create), 조회(Read), 삭제(Delete)할 수 있고, 원하는 노선에 역을 추가(Update)/노선에서 역을 제거(Delete)할 수 있습니다. 지하철 노선도 출력 버튼을 누르면 노선 별로 등록된 역을 조회할 수도 조회할 수 있습니다. 단, 우리가 생각하는 일반적인 역이나 노선 이름의 규칙에서 벗어난 입력은 할 수 없습니다!🚨

## 프로젝트 디렉토리 구조

```sh
├─javascript-subway-map-precourse
│  │
│  ├─docs 
│  │    README.md
│  │
│  │ index.html
│  │
│  ├─src
│  │  │  index.js
│  │  │
│  │  └─modules
│  │      │     
│  │      │  subwayManager.js
│  │      │     
│  │      ├─line
│  │      │     line.js
│  │      │     lineDataHandler.js
│  │      │     lineElemGenerator.js
│  │      │     lineValidator.js
│  │      │
│  │      ├─section
│  │      │     sectionDataHandler.js
│  │      │     sectionElemGenerator.js
│  │      │     sectionValidator.js
│  │      │     
│  │      ├─station
│  │      │     station.js
│  │      │     stationDataHandler.js
│  │      │     stationValidator.js 
│  │      │
│  │      └─util
│  │            constants.js
│  │            events.js
│  │            output.js
│  │      
│  └─images
│          
```

## 👩🏻‍💻 구현할 기능 목록

### 통합적 기능

- `역 관리`, `노선 관리`, `구간 관리`, `지하철 노선도 출력 버튼` 중 하나를 누르면 해당 기능의 내용이 아래에 생성된다. ☑️
- 삭제 버튼을 누를 경우 경고창이 뜨고, 확인을 누를 경우 실제로 삭제가 된다. ☑️
- local storage를 이용하여, 새로고침하더라도 가장 최근에 작업한 정보들을 불러올 수 있도록 해야한다. ☑️
- `역 추가`, `노선 추가`, `등록` 버튼을 누르면 input 칸의 값이 비워진다. ☑️
- 페이지를 새로고침할 때뿐만 아니라 특정 버튼을 클릭할 경우에도 localStorage의 데이터를 새롭게 받아와서 해당하는 요소들을 업데이트 해줘야 한다. ☑️

### 잘못된 입력에 대한 처리

- `alert`를 이용해 메시지를 보여주고, 재입력할 수 있도록 `focus`한다. ☑️

---

### 지하철 역 관련 기능

- 지하철 역을 등록할 수 있어야 한다. ☑️
- 등록된 지하철 역을 삭제할 수 있어야 한다. ☑️
- 등록된 지하철 역의 목록을 표 형식으로 띄워줘야 한다. ☑️

### 지하철 역 관련 기능의 예외

- 노선에 등록된 역은 삭제할 수 없어야 한다. ☑️
- 중복된 지하철 역 이름이 등록될 수 없어야 한다. ☑️
- 2글자 미만의 지하철 역을 등록할 수 없어야 한다. ☑️
- 한글이 아닌 지하철 역 이름은 등록할 수 없어야 한다. ☑️

---

### 지하철 노선 관련 기능

- 등록된 지하철 역을 상행 종점역과 하행 종점역 목록에서 조회할 수 있어야 한다. ☑️
- 지하철 노선을 등록할 수 있어야 한다. ☑️
- 지하철 노선을 삭제할 수 있어야 한다. ☑️
- 노선 등록 시 상행 종점역과 하행 종점역을 입력받아야 한다. ☑️
- `노선 이름`, `상행 종점역`, `하행 종점역`이 포함된 지하철 노선의 목록을 표 형식으로 조회할 수 있어야 한다. ☑️

### 지하철 노선 관련 기능의 예외

- 중복된 지하철 노선 이름이 등록될 수 없어야 한다. ☑️
- 상행 종점역과 하행 종점역이 같으면 등록할 수 없어야 한다. ☑️
- `$문자 + 선`(ex.신분당선) `$숫자 + 호선`(ex.1호선)의 형식에서 벗어난 지하철 노선 이름은 등록할 수 없어야 한다. ☑️

---

### 구간 관리 기능

#### 지하철 구간 추가 기능

- 구간을 수정할 노선을 선택할 수 있어야 한다. ☑️
- 노선을 선택하면 해당 노선 관리 정보가 아래에 뜬다. ☑️
- 등록된 지하철 역 중 하나를 선택하고 삽입할 위치를 입력하면 해당 위치에 역이 추가되고, 원래 그 위치에 있던 역은 한 칸 뒤로 밀려난다. ☑️
- 이미 다른 노선에 등록된 지하철 역도 등록할 수 있다. ☑️

#### 지하철 구간 추가 기능의 예외

- 이미 해당 노선에 등록된 지하철 역은 추가할 수 없어야 한다. ☑️
- 삽입할 위치 인덱스는 `0 ~ 해당 노선에 등록된 역의 수 - 1`의 범위를 벗어날 수 없다. ☑️

#### 지하철 구간 삭제 기능

- 노선에 등록된 역을 제거할 수 있다. ☑️
- 상행 종점을 제거할 경우 다음 역이 상행 종점이 된다. ☑️
- 하행 종점을 제거할 경우 이전 역이 하행 종점이 된다. ☑️

#### 지하철 구간 삭제 기능의 예외

- 노선에 포함된 역이 두개 이하일 때는 역을 제거할 수 없어야 한다. ☑️

---

### 지하철 노선에 등록된 역 조회 기능

- 노선의 상행 종점부터 하행 종점까지 연결된 순서대로 역 목록을 조회할 수 있어야 한다. ☑️
- 이때 역 목록은 `<div class="map"></div>` 태그를 만들고 해당 태그 내부에 노선도를 출력해야 한다. ☑️

<br/>

## 🧐 구현시 고민하고, 이를 통해 배웠던 부분

- 좋은 모듈화란 어떤 것인지에 대해 많이 찾아보기도 했고, 고민도 많이 했습니다. 모듈을 분리 후 이를 통합하기 위한 core를 늘리는 것은 스파게티 코드를 만드는 지름길이라 생각했기 때문에 되도록이면 모듈간 공유하는 core를 줄이기 위해 노력했던 한 주였습니다. 역할과 책임을 기준으로 모듈을 분류하는 것이 기본이겠지만, 특별히 상호작용이 많지 않은(한 쪽의 출력이 한 쪽의 입력으로 사용되는 등) 요소들을 논리적으로 응집시키는 것은 모듈화의 목적을 생각했을 때 맞지 않다고 생각하여 같은 입력을 사용하는 구성 요소 혹은 동일한 출력을 만들어내는 구성요소를 모듈로 묶으려 노력했습니다.

- 이전 과제에서와 같이 향후 변화의 여지가 있는 상수는 한 파일에 모아서 한 곳에서 수정할 수 있도록 했습니다.

- localStorage를 데이터베이스처럼 사용하는 프로그램은 처음이었는데, JavaScript만 사용하다보니 상태 관리가 쉽지 않다고 느꼈습니다. 한 쪽 모듈에서 localStorage의 정보를 수정했는데도 페이지를 리로드하기 전에는 이 내용이 다른 모듈에 반영되지 않는 경우가 많았습니다. JavaScript만으로 프로그램을 짤 때에는 이런 점을 더 주의를 기울여서 설계해야한다는 점을 배웠습니다.

- 비슷한 로직이 여러 모듈에서 사용되는데, 사용하는 element의 id나 이에 따라 조금씩 달라지는 부분들이 있는 메서드들이 많았습니다. 공통되는 요소를 최대한 줄이고 싶었지만, 너무 줄이다보면 향후 모듈간 분리가 쉽지 않을 것 같은데 이런 점을 어떻게 처리해야하는지가 고민이 많이 되었습니다.

- Bubbling과 Capturing의 개념을 공부하고 이를 적용해보았습니다.


## 💻 프로그램 실행 결과

### 역관리

<img width="100%" src="/images/station_manager.gif">

### 노선관리

<img width="100%" src="/images/line_manager.gif">

### 구간관리

<img width="100%" src="/images/section_manager.gif">

### 노선도 출력

<img width="100%" src="/images/map_print_manager.gif">
