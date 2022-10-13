<li><a href="#가위바위보">가위바위보</a></li>
<li><a href="#369게임">369게임</a></li>
<li><a href="#암호해독">암호해독</a></li>
<li><a href="#배열회전시키기">배열회전시키기</a></li>

```html
<section>
  <a name="순서쌍의개수"> #순서쌍의개수</a>
  <h3>
    Q. 순서쌍이란 두 개의 숫자를 순서를 정하여 짝지어 나타낸 쌍으로 (a, b)로
    표기합니다. 자연수 n이 매개변수로 주어질 때 두 숫자의 곱이 n인 자연수
    순서쌍의 개수를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- 1 ≤ n ≤ 1,000,000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 20 결과: 6</p>
  <p>- n: 100 = 결과: 9</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>나머지가 0이 되는 수 찾기 (n % i ===0)</li>
      <li>수가 있다면 answer에 1씩 더하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(n) {
    var answer = 0;
    for(let i=0;i<=n;i++){
     if(n%i ===0)  answer += 1
    } 
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="가위바위보"> #가위바위보</a>
  <h3>
    Q. 가위는 2 바위는 0 보는 5로 표현합니다. 가위 바위 보를 내는 순서대로
    나타낸 문자열 rsp가 매개변수로 주어질 때, rsp에 저장된 가위 바위 보를 모두
    이기는 경우를 순서대로 나타낸 문자열을 return하도록 solution 함수를
    완성해보세요.
  </h3>
  <p>- 0 < rsp의 길이 ≤ 100</p>
  <p>- rsp와 길이가 같은 문자열을 return 합니다.</p>
  <p>- rsp는 숫자 0, 2, 5로 이루어져 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- rsp: "2" 결과: "0"</p>
  <p>- rsp: "205" = 결과: "052"</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>rsp 문자열 배열로 변환</li>
      <li>rsp[i] 값에 따라 answer에 이기는 경우 더하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(rsp) {
    var answer = '';
    rsp.split('')
    for(let i = 0;i＜rsp.length;i++){
        if(rsp[i] === '2') answer += '0'
        if(rsp[i] === '0') answer += '5'
        if(rsp[i] === '5') answer += '2'
    }
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>가위바위보를 이기는 경우를 정의</li>
    <li>[...rsp]를 통해 배열로 변환</li>
    <li>맵 돌면서 value를 이기는 경우의 값으로 바꾸고, 문자열로 변환하기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(rsp) {
    let arr = {
        2: 0,
        0: 5,
        5: 2
    };
    var answer = [...rsp].map(v => arr[v]).join("");
    return answer;
}
  </code>
</pre>
</section>
<section>
  <a name="369게임"> #369게임</a>
  <h3>
    Q. 머쓱이는 친구들과 369게임을 하고 있습니다. 369게임은 1부터 숫자를 하나씩
    대며 3, 6, 9가 들어가는 숫자는 숫자 대신 3, 6, 9의 개수만큼 박수를 치는
    게임입니다. 머쓱이가 말해야하는 숫자 order가 매개변수로 주어질 때, 머쓱이가
    쳐야할 박수 횟수를 return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>- 1 ≤ order ≤ 1,000,000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- order: 3 결과: 1</p>
  <p>- order: 29423 = 결과: 2</p>
  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>order 숫자를 배열로 변환</li>
      <li>v가 3 6 9 인 숫자만 필터링하기</li>
      <li>answer에 array 길이 저장</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(order) {
    var answer = 0;
    const arr = order.toString().split('').filter((v)=>v == 3|| v== 6 || v== 9)
    answer = arr.length
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>1. matchAll(정규표현식)으로 match되는 모든 수 구하기</li>
    <li>2. 3.6.9를 기준으로 배열 나누기</li>
  </ul>
  <pre>
  <code class="javascript">
// 1번
function solution(order) {
    var answer = [...order.toString().matchAll(/[3|6|9]/g)].length;
    return answer;
}

// 2번
function solution(order) {
    return (''+order).split(/[369]/).length-1;
}
  </code>
</pre>
</section>
<section>
  <a name="암호해독"> #암호해독</a>
  <h3>
    Q. 문자열 cipher와 정수 code가 매개변수로 주어질 때 해독된 암호 문자열을
    return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    군 전략가 머쓱이는 전쟁 중 적군이 다음과 같은 암호 체계를 사용한다는 것을
    알아냈습니다.<br />
    - 암호화된 문자열 cipher를 주고받습니다.<br />
    - 그 문자열에서 code의 배수 번째 글자만 진짜 암호입니다.<br />
    문자열 cipher와 정수 code가 매개변수로 주어질 때 해독된 암호 문자열을
    return하도록 solution 함수를 완성해주세요.
  </p>
  <p>
    - 문자열 cipher와 정수 code가 매개변수로 주어질 때 해독된 암호 문자열을
    return하도록 solution 함수를 완성해주세요..
  </p>
  <p>- 1 ≤ cipher의 길이 ≤ 1,000</p>
  <p>- 1 ≤ code ≤ cipher의 길이</p>
  <p>- cipher는 소문자와 공백으로만 구성되어 있습니다.</p>
  <p>- 공백도 하나의 문자로 취급합니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- cipher: "dfjardstddetckdaccccdegk" code: 4 결과: "attack"</p>
  <p>- cipher: "pfqallllabwaoclk" code: 2 결과: "fallback"</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>cipher의 길이에서 code로 나눈 값만큼 반복</li>
      <li>cipher의 [i * code -1]한 값 더하기 (code의 배수)</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(cipher, code) {
    var answer = '';
    for(let i = 1; i<=cipher.length / code;i++){
        answer += cipher[i * code -1]
    }
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>변수 i를 code -1로 설정 (index는 0부터 시작하니까)</li>
    <li>cipher.length만큼 반복</li>
    <li>변수 i의 증감을 code만큼 더하기 (3 + 4 + 7 ...)</li>
    <li>cipher[i] 더하기</li>
    <li>※내 코드랑 비슷하지만 더 간단하고, 읽기 쉬움</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(cipher, code) {
  var answer = "";
  for (let i = code - 1; i < cipher.length; i += code) {
    answer += cipher[i];
  }
  return answer;
}
  </code>
</pre>
</section>
<section>
  <a name="배열회전시키기"> #배열회전시키기</a>
  <h3>
    Q. 정수가 담긴 배열 numbers와 문자열 direction가 매개변수로 주어집니다. 배열
    numbers의 원소를 direction방향으로 한 칸씩 회전시킨 배열을 return하도록
    solution 함수를 완성해주세요.
  </h3>
  <p>- 1 ≤ numbers의 길이 ≤ 100</p>
  <p>- direction은 "left" 와 "right" 둘 중 하나입니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- numbers: [1, 2, 3] direction: "right" 결과: [3, 1, 2]</p>
  <p>
    - numbers: [4, 455, 6, 4, -1, 45, 6] direction: "left" 결과: [455, 6, 4, -1,
    45, 6, 4]
  </p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>
        방향이 오른쪽일 경우, 복사한 numbers 배열에서 0 ~ 마지막 -1 까지
        잘라내고
      </li>
      <li>마지막 인덱스를 새로운 배열 맨 앞에 집어넣기</li>
      <li>방향이 오른쪽일경우, 복사한 배열에서 1~마지막까지 잘라내고</li>
      <li>맨앞 인덱스를 새로운 배열 맨 뒤에 집어넣기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(numbers, direction) {
    var answer = [];
    if(direction === 'right') {
        answer = [...numbers].splice(0,numbers.length -1)
        answer.unshift(numbers[numbers.length-1])
    }else{
        answer = [...numbers].splice(1,numbers.length)
        answer.push(numbers[0])
    }
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>배열.pop()이용해서 배열 맨 뒤 값 추출</li>
    <li>numbers 배열에 마지막 값 맨 앞에 집어넣기</li>
    <li>배열.shift()이용해서 배열 맨 앞 값 추출</li>
    <li>numbers 배열에 처음 값 맨 뒤에 집어넣기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(numbers, direction) {
    var answer = [];

    if ("right" == direction) {
        numbers.unshift(numbers.pop());
    } else {
        numbers.push(numbers.shift());
    }

    answer = numbers;

    return answer;
}
  </code>
</pre>
</section>
```

```html
<section>
  <a name="최솟값만들기"> #최솟값만들기</a>
  <h3>
    Q. 배열 A, B가 주어질 때 최종적으로 누적된 최솟값을 return 하는 solution
    함수를 완성해 주세요.
  </h3>
  <p>
    길이가 같은 배열 A, B 두개가 있습니다. 각 배열은 자연수로 이루어져
    있습니다.<br />
    배열 A, B에서 각각 한 개의 숫자를 뽑아 두 수를 곱합니다. 이러한 과정을
    배열의 길이만큼 반복하며, 두 수를 곱한 값을 누적하여 더합니다. 이때
    최종적으로 누적된 값이 최소가 되도록 만드는 것이 목표입니다. (단, 각
    배열에서 k번째 숫자를 뽑았다면 다음에 k번째 숫자는 다시 뽑을 수
    없습니다.)<br />
    예를 들어 A = [1, 4, 2] , B = [5, 4, 4] 라면
  </p>
  <p>
    - A에서 첫번째 숫자인 1, B에서 첫번째 숫자인 5를 뽑아 곱하여 더합니다.
    (누적된 값 : 0 + 5(1x5) = 5)
  </p>
  <p>
    - A에서 두번째 숫자인 4, B에서 세번째 숫자인 4를 뽑아 곱하여 더합니다.
    (누적된 값 : 5 + 16(4x4) = 21)
  </p>
  <p>
    - A에서 세번째 숫자인 2, B에서 두번째 숫자인 4를 뽑아 곱하여 더합니다.
    (누적된 값 : 21 + 8(2x4) = 29)
  </p>

  <br />
  <p>
    즉, 이 경우가 최소가 되므로 29를 return 합니다.<br />

    배열 A, B가 주어질 때 최종적으로 누적된 최솟값을 return 하는 solution 함수를
    완성해 주세요.
  </p>
  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- A: [1, 4, 2] B: [5, 4, 4] = 결과: 29</p>
  <p>- A: [1,2] B: [3,4] = 결과: 10</p>

  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>
        A 올림 차순으로 정렬(낮은 순서대로), B: 내림차순으로 정렬(높은 순서대로)
      </li>
      <li>가장 낮은 수 * 가장 높은 수</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(A,B){
    var answer = 0;
    A.sort((a,b)=>a-b)
    B.sort((a,b)=>b-a)
  
    for(let i = 0; i < A.length;i++){
     answer += A[i] * B[i]
    }

    return answer;
}
  </code>
</pre>
  <hr />
  <br />

  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>A,B 정렬</li>
    <li>reduce로 결과값 구하기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(A,B){
    A.sort((a, b) => a - b)
    B.sort((a, b) => b - a)
    return A.reduce((total, val, idx) => total + val * B[idx], 0)
}
  </code>
</pre>
</section>
```
