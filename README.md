# 자바스크립트 코딩 테스트 공부

### Q. 정수를 담고 있는 배열 arr의 평균값을 return 하는 함수, solution을 완성해보세요.

arr은 길이 1이상 100이하인 배열입니다.
arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

예)
arr | return
|:--:|:--:|
[1,2,3,4] | 2.5
[5,5] | 5

<Br>
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

---

### Q. 프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다. 전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 \*으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

" phone_number는 길이 4 이상, 20이하인 문자열입니다.

입출력 예

| phone_number  |      return      |
| :-----------: | :--------------: |
| "01033334444" | "**\*\*\***4444" |
|  "027778888"  |   "**\***8888"   |

<Br>

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

---

---

### Q. 정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요

num은 int 범위의 정수입니다.
0은 짝수입니다.

입출력 예
num| return
|:--:|:--:|
3 | "Odd"
4 | "Even"

<br>
풀이

```js
function solution(num) {
  if (num / 2) {
    return "Even";
  } else {
    return "Odd";
  }
}

// 삼항연산자
function solution(num) {
  const answer = num % 2 ? "Odd" : "Even";
  return answer;
}
```

---

---

### Q. 행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

입출력 예

|     arr1      |     arr2      |    return     |
| :-----------: | :-----------: | :-----------: |
| [[1,2],[2,3]] | [[3,4],[5,6]] | [[4,6],[7,9]] |
|   [[1],[2]]   |   [[3],[4]]   |   [[4],[6]]   |

<br>
풀이)

```js
function solution(arr1, arr2) {
  let result = [];
  for (let i = 0; i < arr1.length; i++) {
    result.push([]);
    for (let j = 0; j < arr1[i].length; j++) {
      const sum = arr1[i][j] + arr2[i][j];
      result[i].push(sum);
    }
  }
  return result;
}

// map()
function solution(arr1, arr2) {
  return arr1.map((a, i) => a.map((b, j) => b + arr2[i][j]));
}
```

```js
arr1 = [[1,2],[2,3]]
arr2 = [[3,4],[5,6]]
result =  [[4,6],[7,9]]

arr1[0][0] + arr2[0][0] = result[0][0]
// 1 + 3 = 4
arr1[0][1] + arr2[0][1] = result[0][1]
// 2 + 4 = 6

...반복

위 내용을 반복하는 반복문 코드 작성
```

---

---

#### Q. 자연수 n이 매개변수로 주어집니다. n을 x로 나눈 나머지가 1이 되도록 하는 가장 작은 자연수 x를 return 하도록 solution 함수를 완성해주세요. 답이 항상 존재함은 증명될 수 있습니다.

입출력 예  
n| result  
|:--:|:--:|
10| 3  
12| 11

입출력 예 #1
10을 3으로 나눈 나머지가 1이고, 3보다 작은 자연수 중에서 문제의 조건을 만족하는 수가 없으므로, 3을 return 해야 합니다.

입출력 예 #2
12를 11로 나눈 나머지가 1이고, 11보다 작은 자연수 중에서 문제의 조건을 만족하는 수가 없으므로, 11을 return 해야 합니다.
<br>
풀이)

```js
function solution(n) {
  let result = 0;
  for (let i = 0; i < n; i++) {
    if (n % i === 1) {
      result = i;
      break;
    }
  }
  return result;
}
```

> break를 해서 코드를 멈추지 않으면 계속 for문이 실행됨..

---

---

### Q. 두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution을 완성하세요.

예를 들어 a = 3, b = 5인 경우, 3 + 4 + 5 = 12이므로 12를 리턴합니다.

a와 b가 같은 경우는 둘 중 아무 수나 리턴하세요.
a와 b는 -10,000,000 이상 10,000,000 이하인 정수입니다.
a와 b의 대소관계는 정해져있지 않습니다.

입출력 예)

|  a  |  b  | return |
| :-: | :-: | :----: |
|  3  |  5  |   12   |
|  3  |  3  |   3    |
|  5  |  3  |   12   |

<br>

풀이)

```js
function solution(a, b) {
  let result = 0;
  for (let i = Math.min(a, b); i <= Math.max(a, b); i++) {
    result += i;
  }
  return result;
}
```

> a와 b 중의 가장 작은 값부터, 가장 큰 값까지 반복문을 통해 총합 구하기

Math.min() / Math.max()

- 주어진 숫자들 중 가장 작은 값/ 큰 값을 반환

---

---

참고

- https://hw1205.tistory.com/45
- enai.tistory.com
