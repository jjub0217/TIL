

# 배치3 (flex)

## 3. flex

- 수평이나 수직으로 정렬을 해주는 속성

1. container (container에서 display 의 flex를 부여)

   - container 안의 요소들은 items 들이 된다. (= items 들을 감싸는 부모요소가 된다 )

   - 각 items 들을 정렬시키기 위해서는 container 는 필수적인 개념이다. 

   - flex container( 부모요소 ) 에서 사용할수 있는 속성

     a. **<u>display</u>** ( 요소의 특성을 정의 : block 으로 할지, inline 으로 할지, flex 로 할지)

     1. block /inline

     2. flex / inline-flex

        - flex : ( container 가 **block 요소화가 된다: 수직정렬** ) flex container가 되면서 container 내부에 items 생성

        - container 에 display : flex 를 부여하면 내부의 item 들은 수평정렬이 된다.

        - 예시

          ```html
          <div class="container1">
              <div class="item">1</div>
              <div class="item">2</div>
              <div class="item">3</div>
          </div>
          <div class="container2">
              <div class="item">1</div>
              <div class="item">2</div>
              <div class="item">3</div>
          </div>
          ```

          ```css
          .container1 {
              display: flex;
          }
          .container2 {
              display: flex;
          }
          ```

          **"수직정렬"**

          ![캡처28](https://user-images.githubusercontent.com/62126380/79680871-94e0a900-824f-11ea-9bd5-4317cd9359b0.PNG) 

          

        - inline-flex :  ( container 가 **inline 요소화가 된다: 수평정렬** ) flex container가 되면서 container 내부에 items 생성

        - 예시

          ```html
          <div class="container1">
              <div class="item">1</div>
              <div class="item">2</div>
              <div class="item">3</div>
          </div>
          <div class="container2">
              <div class="item">1</div>
              <div class="item">2</div>
              <div class="item">3</div>
          </div>
          ```

          ```css
          .container1 {
              display: inline-flex;
          }
          .container2 {
              display:inline-flex;
          }
          ```

          **"수평정렬"**

          ![캡처29](https://user-images.githubusercontent.com/62126380/79680901-cce7ec00-824f-11ea-84de-98dab447c336.PNG) 

     ---

     b. **<u>flex-flow</u>**( 단축속성 ) : *" flex-flow : 주축(flex-direction) 여러줄묶음(flex-wrap) "*

     ```css
     flex-flow: (flex-direction:row) (flex-wrap:no-wrap)
     ```

      1. flex-direction : item 들의 주 축을 설정

         - 수평정렬 : row ( 왼 -> 오 ) / row-reverse ( 오 -> 왼 )

           **"row"**           ![캡처30](https://user-images.githubusercontent.com/62126380/79681052-8bf0d700-8251-11ea-84d8-95129a128ad5.PNG) **"row-reverse"** ![캡처31](https://user-images.githubusercontent.com/62126380/79681114-3832bd80-8252-11ea-8be3-d4edc402ca95.PNG)

           ---
         
- 수직정렬 : colum ( 위 -> 아래 ) /cloumn-reverse( 아래 -> 위)
	
	**column"**		![캡처32](https://user-images.githubusercontent.com/62126380/79681217-5fd65580-8253-11ea-99be-e4859d967284.PNG) **"column-reverse"** ![캡처33](https://user-images.githubusercontent.com/62126380/79681250-b80d5780-8253-11ea-998d-9ddfb18f3dd5.PNG) 
    
    ---
2. flex-wrap ( item 들의 줄을 여러줄 혹은 안 여러줄로 설정)
   
     - container 안에 들어있는 각각의 item 들을 여러줄로 할것인지, 한줄로 할것인지 설정
     
     - container 안에 있는 item들의 가로너비는 container의 가로 너비에 따라 크기가 가변할 수 있다. 
       - 속성값
         - nowrap( 한줄에 표시)
           - wrap ( 여러줄에 표시 )
             - wrap-reverse (역방향으로 여러줄에 표시) : wrap 한 줄을 앞뒤로 뒤바꿈
```html
  <div class="container ">
      <div class="item">A</div>
      <div class="item">B</div>
      <div class="item">C</div>
<div class="item">D</div>
         <div class="item">E</div>
     </div>
```

```css
 .container {
     border: 4px solid;
     display: flex;
     flex-wrap: wrap; /*<- 각각의 요소들은 자신이 원래 가지고 있었던 너비 그대로 가지고 가며,
                           칸이 모자르니까 자연스럽게 줄바꿈이 된다.*/
 }
 
 .container .item {
     width: 150px; /*<-  컨테이너 안에 있는 각각의 아이템들은 
     					가로너비가 부모요소에 맞춰져서 한줄안에 다 들어가게 된다.
                         각각의 아이템들은 flex-basis 라는 속성을 auto라는 기본값으로 갖고 있는데 
                         flex-basis 값이 auto인 경우에는 가로세로너비 가 가변된다. */
    height: 100px;
    background: tomato;
	border: 4px dashed red;
    border-radius: 10px;
}
```
---

 c.  **<u>justify-content</u>** ( **주 축(메인축)의 정렬방법을 설정** )

```html
 <div class="container ">
     <div class="item">A</div>
<div class="item">B</div>
     <div class="item">C</div>
</div>
```

  1. flex-start : 시작점을 기준으로 해서 왼쪽 정렬 ![캡처34](https://user-images.githubusercontent.com/62126380/79681853-a0849d80-8258-11ea-8121-d7ed905d0ff3.PNG) 

     ```css
     .container {
         border: 1px solid red;
         justify-content: flex-start;
     }
     
     .container .item {
         width: 100px;
         height: 100px;
         border: 1px solid;
     }
     ```

  2. flex-end : 끝점을 기준으로 해서 오른쪽 정렬 ![캡처35](https://user-images.githubusercontent.com/62126380/79681884-ee010a80-8258-11ea-9060-7bab3ea1bfd8.PNG)

     ```css
     .container {
         border: 1px solid red;
         justify-content: flex-end;
     }
     
     .container .item {
         width: 100px;
         height: 100px;
         border: 1px solid;
     }
     ```

  3. center : 가운데 정렬  ![캡처36](https://user-images.githubusercontent.com/62126380/79681917-31f40f80-8259-11ea-8c78-8bf9d4180290.PNG) 

     ```css
     .container {
         border: 1px solid red;
         justify-content: center;
     }
     
     .container .item {
         width: 100px;
         height: 100px;
         border: 1px solid;
     }
     ```

  4. space-between  ![캡처37](https://user-images.githubusercontent.com/62126380/79682005-c8c0cc00-8259-11ea-9350-4abdcccea2d5.PNG) 

     - 첫번째와, 마지막 아이템을 각각 시작점과 끝점에 붙히고, 남은 여백을 균등하게 가운데 정렬

     ```css
     .container {
         border: 1px solid red;
         justify-content: space-between;
     }
     
     .container .item {
         width: 100px;
         height: 100px;
         border: 1px solid;
     }
     ```

  5. space-around : 쓸데없는 여백없이 꽉꽉 채워서 가운데 정렬 ![캡처38](https://user-images.githubusercontent.com/62126380/79682049-20f7ce00-825a-11ea-91c0-8a11f8b91af7.PNG) 

     ```css
     .container {
         border: 1px solid red;
         justify-content: space-around;
     }
     
     .container .item {
         width: 100px;
         height: 100px;
         border: 1px solid;
     }
     ```

---

 d. <u>align-content</u>  / **<u>align-items</u>** ( 교차 축의 정렬 방법을 설정 )

 - **<u>align-content</u>** 

   - **<u>"flex-wrap 을 이용해서 item 이 2줄 이상이어야만, 그리고 여백이 있어야만 사용가능"</u>**

   - container의 높이가 fix 되서 여백이 있고 여러줄일때만 동작한다.

     ```html
     <div class="container ">
         <div class="item">A</div>
         <div class="item">B</div>
         <div class="item">C</div>
         <div class="item">D</div>
         <div class="item">E</div>
      	<div class="item">F</div>
     </div>
     ```
     
       ```css
     .container {
       display: flex;	/*<- container에 display flex 를 부여하고,*/
       flex-wrap: wrap;/*<- flex-wrap 으로 두줄을 만들고,*/
       align-content: center;/*<- 두줄이며, 여백이 있으므로 "align-content" 를 사용해서 정렬*/
     
     }
     
     .container .item {
       width: 120px;
     height: 100px;
       background: tomato;
     }
       ```

     1. stretch( 기본값 )
      2. flex-start
        3. flex-end
      4. center
     5. space-between
     6. space-around

   ---
- <u>**align-items**</u> 

  - item이 한줄이어야만 사용가능
  - align-content 속성을 기본값 stretch 로 해야만 사용가능 

  ```html
  <div class="container ">
      <div class="item">A</div>
      <div class="item">B</div>
      <div class="item">C</div>
      <div class="item">D</div>
      <div class="item">E</div>
      <div class="item">F</div>
  </div>
  ```
```css
.container {
  display: flex; /*<- 내부에 있는 item들을 수평정렬 하기 위해 display flex 를 부여*/
}

.container .item {
  width: 120px;
  height: 100px;
  background: tomato;
  display: flex; /*<- item 에 삽입되어있는 텍스트들을 중앙정렬 하기 위해, 
                    item들도 container화 하기 위해 display flex 를 부여*/
  justify-content: center; /*<- 현재 주축이 가로축이기 때문에 가로축을 주축으로 가운데 정렬시킴*/
align-items: center; /*<- 가로축에서 중앙정렬이 된 텍스트들을 세로축에서도 중앙정렬을 시키기 위헤
                           align-items center 를 부여*/
}
```

  1. stretch( 기본값 )
   2. flex-start
   3. flex-end
   4. center
  5. baseline

![캡처39 PNG](https://user-images.githubusercontent.com/62126380/87371512-83920900-c5c0-11ea-9f8e-c0d919471948.jpg)   

2. items ( container에 display의 flex를 부여한 상태의 내부 요소인 items )

   - flex items 에 사용할 수 있는 속성

     a. <u>**order**</u> ( flex items 의 순서를 설정)

     - 각각의 item 의 순서를 설정

     - HTML 구조 순서 상관없이 순서 변경 가능

     - item에 숫자를 지정하여 해당 그 숫자가 작을수록 앞으로 온다. 

     - 음수 사용 가능

     - 예시 ![캡처132](https://user-images.githubusercontent.com/62126380/87424183-80c20300-c616-11ea-9811-f0f18928bcb4.PNG)  

       ```html
       <div class="container ">
           <div class="item item1">1</div>
           <div class="item item2">2</div>
           <div class="item item3">3</div>
           <div class="item item4">4</div>
           <div class="item item5">5</div>
           <div class="item item6">6</div>
       </div>
       ```

       ```css
       .item1 {
           order: 1;
       }
       
       .item4 {
           order: 1;
       }
       
       .item6 {
           order: -1;
       }
       ```

     b. flex( 단축속성 ) : *" flex: *증가너비 비율(flex-glow: 기본값 0) 감소너비 비율(flex-shrink: 기본값 1) 기본너비(flex-basis: 기본값 auto)"* *

     1. flex-glow : flex-item 의 증가너비 비율 설정

        ![캡쳐200](https://user-images.githubusercontent.com/62126380/87425464-ab14c000-c618-11ea-8ff6-4ec16d5a36a3.PNG) 

        ```html
         <div class="container1">
            <div class="item item1">1</div>
            <div class="item item2">2</div>
            <div class="item item3">3</div>
        
        </div>
        ```

        ```css
         .container1 .item1 {
            flex-grow: 5; /*<- 50% = 5/(5 + 4 + 1) */
        }
        .container1 .item2 {
            flex-grow: 4; /*<- 40% = 4/(5 + 4 + 1) */
        }
        
        .container1 .item3 {
            flex-grow: 1; /*<- 10% = 1/(5 + 4 + 1) */
        }
        
        ```

     2. flex-shrink : flex-item 의 감소너비 비율 설정

     3. flex-basis : flex-item 의 기본너비 비율 설정

     ---
     
     c. align-self : item 하나에만 일시적으로 설정 ( 교차축에서 item의 정렬 방법 설정 )

