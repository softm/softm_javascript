<div class="markdown-body">
<h1>d3 enter</h1>

##### [source : https://jsfiddle.net/softm/q1ofn8tL](https://jsfiddle.net/softm/q1ofn8tL)

```css
<style>
   circle {
     stroke: black;
     stroke-width: 1.5px;
     fill: steelblue;
   }

   text {
     stroke: white;
     text-anchor: middle;
   }

   path {
     stroke: darkgrey;
     stroke-width: 2px;
     fill: none;
   }
</style>
```

```javascript
<script>
     //window.onload = function() {
        var dataset = [ 5, 10, 15, 20, 25 ];
        d3.select("div")          // 1
                .selectAll("p")          // 2
                .data(dataset)           // 3
                .enter()                 // 4
                .append("p")             // 5
                .text("New paragraph!"); // 6

        d3.selectAll("p").style("color", function() {
            return "hsl(" + Math.random() * 360 + ",100%,50%)";
        });

        /* 
        d3.selectAll("p").style("color", function(d, i) {
            return i % 2 ? "#fff" : "#eee";
        }); 
         */

        d3.selectAll("p")
                .data([4, 8, 15, 16, 23, 42])
                .style("font-size", function(d) { return d + "px"; });
    //}
<script>
```



<xmp>
// 1. select를    이용해 body태그 요소를 찾는다.
// 2. selectAll을 이용해 p태그 요소를 찾는다.
// 3. data를 이용해 array의 크기만큼의 가상의 데이터 구조를 만든다.
// 4. enter를 이용해 현재영역(p태그)의 상위영역으로 데이터처리영역으로 진입시킨다. ( p태그의 상위영역 body으로 데이터처리할 영역이 설정된다. )
//    enter는 기존에 존재하는 영역에는 영역을 만들지 않는다
//    예를 들어 p로 선택된 영역이 아래처럼 3개의 영역이 있다면
//        <p>test1</p>
//        <p>test2</p>
//        <p>test3</p>
//    dataset의 갯수 5개 기준 두개의 영역만 enter에의해 진입된 영역으로서 이용된다.
//      다시말하면 test1,test2, test3영역은 조작할 수 없다는 말이다.
//        <p>test1</p>
//        <p>test2</p>
//        <p>test3</p>        
//        <p>20</p>         
//        <p>25</p>
</xmp>

<div style="background-color: skyblue">
    <p>test1</p>
    <p>test2</p>
    <p>test3</p>    
</div>
</div>