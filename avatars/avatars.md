# 1. 기본 설정
- ```npm run dev```가 안돼서, 영상을 참고해 ```fiverserver.config.js```를 깔고 수업에 사용했던 ```basic-ui``` 폴더의 ```fiverserver.config.js 파일```과 ```package.json```의 코드를 복사해서 가져왔다. ```npm run dev```가 실행됐지만 8086 포트는 이미 다른 파일에서 쓰고 있다고 나와서 결국엔 사용하지 못했다. 그래서 일단은 **라이브서버**로 진행했다.  
<br>

# 2. 구조 설계, 이미지 배치
- 여자그룹에는 ```float:left;```를 줬고, 남자그룹에는 ```clear:both;```를 주었다. 개발자도구의 style 탭에서도 적용됐음을 확인했다.<br>   
(* 질문 : 그렇지만, ```div 태그```로 남자와 여자 그룹을 나누면 애초에 ```div 태그```가 박스형태로 구현되기 때문에 줄이 나뉜다. 두 줄이 나뉘는 형태를 만들기 위해 꼭 ```float```를 적용해야 하는 이유가 따로 있을까?)   
<br>

- 좌우의 마진 값은 병합되지 않기 때문에, 마진을 전체 이미지에 10px씩 주었다.  
<br>

# 3. 모든 이미지 원 형태 구현
- 모든 이미지 원 형태로 만들기 : ```border-radius : 50%;```  
<br>

# 4. 회색 원, 초록색 원 만들기
- 회색 원, 초록색 원 만들기 : ```class="circle;"```로 ```div 태그```를 만들고, 1번/3번/6번/8번 이미지의 원은 회색으로 설정하고 2번/4번/7번/5번 이미지의 원은 초록색으로 설정했다.   
<br>

# 5. 회색원, 초록색 원 위치 설정
* ```position```을 이용한 회색원, 초록색 원 위치 설정 
  - 여자 이미지와 남자 이미지에 겹쳐질 online/offline 상태를 나타내는 원 형태를 ```<section woman-circle>```과 ```<section man-circle>```로 각각 그룹핑하여 부모 컨테이너인 ```<div class=`woman'>```과 ```<div class='man'>```에 포함시켰다.

  * 첫번째 이미지의 online/offline 원을 나타내는 ```circle no.1```부터 마지막 이미지의 online/offline 원을 나타내는 ```circle no.8```까지 각각 ```position: absolute;``` 속성을 부여하고 상위 태그인 여자 그룹과 남자 그룹에는 ```position: relative;```를 부여하여 모두 각자의 부모 컨테이너를 기준으로 자리를 잡을 수 있도록 만들었다.    
  <br>

# 6. flex를 지원하는 환경 한정 레이아웃
```
@supports (display: flex){
  .group {
    display: flex;
    flex-direction: column-reverse;
  }
}
```
- flex를 지원하는 환경에서는 여자이미지 그룹과 남자 이미지 그룹의 배치 순서가 다르다. 여자 그룹과 남자 그룹을 모두 포함하는 부모 컨테이너인 ```<class="group">```에 ```display: flex;```와 ```flex-direction: colum-reverse;```를 부여해 flex 아이템의 배치 방향을 역순으로 새로 배치할 수 있도록 만들었다. 












