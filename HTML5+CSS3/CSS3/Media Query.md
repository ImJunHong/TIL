# Media Query
* 다양한 장치에서 HTML 문서가 적절한 형태를 갖추게 함
* 반응형 웹을 구현할 수 있음
* <link> 태그 내에서 media 속성을 통해 입력하거나, CSS에 직접 입력

## 기본 구문
```css
@media media-type and (media-feature-rule) {
  /* CSS code */
}
```
### 미디어 유형
* all (모든 장치)
* print (프린터 기기)
* screen (스크린이 있는 기기)
* speech (웹 페이지를 읽어주는 스크린 리더)

### 특성
* width/height (뷰포트 너비/높이)
* aspect-ratio (뷰포트의 가로세로 비율)
* device-width/height (장치의 너비/높이)
* device-aspect-ratio (장치의 가로세로 비율)
* orientation (장치의 방향)
* resolution (장치의 해상도)
* orientation을 제외한 속성은 min-과 max- 접두사를 사용할 수 있음

## Mobile First
* 모바일에 대한 스타일이 우선 적용되도록 min-width 활용
```css
html {font-size: 15px;}
@media screen and (min-width: 640px) {
    html {font-size: 18px;}
}
@media screen and (min-width: 768px) {
    html {font-size: 21px;}
}
@media screen and (min-width: 1024px) {
    html {font-size: 24px;}
}
```

## Desktop First
* 데스크탑에 대한 스타일이 우선 적용되도록 max-width 활용
```css
html {font-size: 24px;}
@media screen and (max-width: 1023px) {
    html {font-size: 21px;}
}
@media screen and (max-width: 767px) {
    html {font-size: 18px;}
}
@media screen and (max-width: 639px) {
    html {font-size: 15px;}
}
```
