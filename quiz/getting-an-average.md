# 평균 구하기

## 문제
함수를 완성해서 매개변수 array의 평균값을 return하도록 만들어 보세요.  
어떠한 크기의 array가 와도 평균값을 구할 수 있어야 합니다.

[문제 링크(프로그래머스)](https://programmers.co.kr/learn/challenge_codes/126){:target="_blank"}

## 나의 풀이

```js
function average(array){
  var sum = 0, avg = 0;
  for(var i=0; i<array.length; i++) {
    sum += array[i];
  }
  avg = sum / array.length
  return avg;
}


// 아래는 테스트로 출력해 보기 위한 코드입니다.
var testArray = [5,3,4] 
console.log("평균값 : " + average(testArray));
```

## 다른 사람의 풀이

`avg`변수를 굳이 따로 할당하지 않으면 코드를 좀 더 줄일 수 있다.


```js
function average(array){
  var sum = 0;
  for(var i=0; i<array.length; i++) {
    sum += array[i];
  }
  return sum / array.length;
}
```

`reduce`함수를 사용하는 방법도 있는데...흠 어렵다.

```js
function average(array){
  return array.reduce((a, b) => a + b) / array.length;
}
```

`reduce`함수는 배열의 각 원소를 돌면서 콜백 함수를 반복적으로 적용하여 하나의 값을 뽑아내는 함수이다. 아래는 배열을 돌면서 각 원소의 총합을 리턴하는 코드이다.


```js
var array = [1, 2, 3, 4, 5];
array.reduce(function(a, b){return a + b}); // 15
```

다음의 코드도 마찬가지이다.

```js
function add(acc, value) {
  return acc + value;
}
[1, 2, 3, 4, 5].reduce(add, 0); // 15
````

이 코드의 실행 결과는 add(add(add(add(add(0, 1), 2), 3), 4), 5)와 같다.  
`reduce`의 두 번째 인자가 acc의 초기값이 되고, 이후 각 원소를 덧셈한 결과가 계속 acc에 누적되어 넘어가는 방식이다.

[참고 링크](https://gamecodingschool.org/2015/06/16/javascript-reduce-%ED%95%A8%EC%88%98/){:target="_blank"}



