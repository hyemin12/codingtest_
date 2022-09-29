# 자바스크립트 코딩 테스트 공부

### Q. 정수를 담고 있는 배열 arr의 평균값을 return 하는 함수, solution을 완성해보세요.

```
arr은 길이 1이상 100이하인 배열입니다.
arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

예)
arr return
[1,2,3,4] 2.5
[5,5] 5
```

풀이)

```js
function solution(arr) {
  let result = 0;
  const reducer = (previousValue, currentValue) => previousValue + currentValue;

  if (arr) {
    result = array1.reduce(reducer) / array1.length;
  }
}
```

Arr.reduce()

- 배열의 각 요소에 대해 주어진 **리듀서**(reducer) 함수를 실행하고, 하나의 결과값을 반환
- 배열에 있는 값을 모두 더함(누산기)

```js
array1.reduce(
  (previousValue, currentValue) => previousValue + currentValue
```

---

### Q.

```
프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다. 전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 \*으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.
* phone_number는 길이 4 이상, 20이하인 문자열입니다.

입출력 예

phone_number return
"01033334444" "*******4444"
"027778888" "*****8888"
```

풀이)

```js
function solution() {
  let result = "";
  const pNumber = phone_number.slice(-4);
  for (let i; i < phone_number.length - 4; i++) {
    result = +"*";
  }
  return result + pNumber;
}
```

Array.slice(begin, end)

- begin : 0을 시작으로 하는 추출 시작점에 대한 인덱스
- end: 추출을 종료할 0 기준 인덱스, end 생략시 배열의 끝까지 추출함

```js
const arr = [0, 1, 2, 3, 4, 5];

// index 2 ~ 4 까지 추출
const res = arr.slice(1, 4);

// index 2 ~ 끝에서 2번째까지 추출
const res2 = arr.slice(2, -1);

console.log(res);
// [2, 3]
console.log(res2);
// [2, 3, 4]
```
