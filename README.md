# loading-btn
API 요청과 같은 비동기 요청시 로딩 표기를 위한 버튼 컴포넌트입니다.\
컴포넌트를 사용하는 부분에서 최대한 간단하게 사용할 수 있도록 만들어 봤습니다.

## 컴포넌트 사용 예시
```javascript
//basic
<loading-button title="버튼 문구" :click-func="버튼클릭시 동작할 메소드"/>
//class 지정이 필요할때
<loading-button class-nm="클래스명" ... />
//메소드에 전달할 파라미터
<loading-button :func-param="메소드로 넘길 파라미터" ... />
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```
