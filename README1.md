<li><a href="#모음제거">모음제거</a></li>

```html
<section>
  <a name="k의개수"> #k의개수</a>
  <h3>
    Q. 1부터 13까지의 수에서, 1은 1, 10, 11, 12, 13 이렇게 총 6번 등장합니다.
    정수 i, j, k가 매개변수로 주어질 때, i부터 j까지 k가 몇 번 등장하는지 return
    하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- 1 ≤ i < j ≤ 100,000</p>
  <p>- 0 ≤ k ≤ 9</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- i: 1 j: 13 k: 1 결과: 6</p>
  <p>- i: 10 j: 50 k: 5 결과: 5</p>
  <p>- i: 3 j: 10 k: 2 결과: 0</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>Array().fill().map() 을 통해 i부터 j까지 배열을 만들고,</li>
      <li>// Array(배열의 개수) //.fill() 채우기</li>
      <li>배열을 합치고, 다시 한자리수로 쪼개서 배열로 만들기</li>
      <li>k와 같은 숫자만 필터링하고, 길이 반환하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(i, j, k) {
    var answer = 0;
    let arr = Array(j - i +1).fill().map((a,idx)=> i+idx).join('').split('')
    answer = arr.filter((v)=> parseInt(v) === k).length
    
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>변수로 제공된 i를 활용하여 for문 작성</li>
    <li>i를 배열로 바꾸고, k를 기준으로 쪼개기</li>
    <li>길이 -1의 값을 answer에 더해주고 결과값 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(i, j, k) {
    var answer = 0;

    for(; i<=j; i++) {
        const x = i.toString().split(k).length-1;
        answer += x;        
    }

    return answer;
}
  </code>
</pre>
</section>
<section>
  <a name="한번만등장한문자"> #한번만등장한문자</a>
  <h3>
    Q. 문자열 s가 매개변수로 주어집니다. s에서 한 번만 등장하는 문자를 사전
    순으로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요. 한 번만
    등장하는 문자가 없을 경우 빈 문자열을 return 합니다.
  </h3>
  <p>- 0 < s의 길이 < 1,000</p>
  <p>- s는 소문자로만 이루어져 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- s : "abcabcadc"결과: "d"</p>
  <p>- s : "abdc" 결과: "abcd"</p>
  <p>- s : "hello" 결과: "eho""</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>중복제거한 문자열 배열 만들기</li>
      <li>s 배열 필터링 하면서 길이가 1개일 경우 answer에 집어넣기</li>
      <li>오름차순으로 정렬하고, 문자열로 변환해서 반환</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(s) {
    var answer = [];
    const arr = [...new Set(s)]
    for(let i =0;i＜s.length;i++){
       const count = s.split('').filter((v)=>v === arr[i]).length
       count === 1 ? answer.push(arr[i]) : ''
       }
    answer = answer.sort().join('')
    return answer;
}
    </code></pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>인덱스 값고, 마지막 인덱스값이 같을 경우 res에 집어넣기</li>
    <li>오름차순 정렬 후 문자열로 변환 하고 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(s) {
    let res = [];
    for (let c of s) if (s.indexOf(c) === s.lastIndexOf(c)) res.push(c);
    return res.sort().join('');
}
  </code>
</pre>
</section>
<section>
  <a name="팩토리얼"> #팩토리얼</a>
  <h3>
    Q. i팩토리얼 (i!)은 1부터 i까지 정수의 곱을 의미합니다. 예를들어 5! = 5 * 4
    * 3 * 2 * 1 = 120 입니다. 정수 n이 주어질 때 다음 조건을 만족하는 가장 큰
    정수 i를 return 하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- i! ≤ n</p>
  <p>- 0 < n ≤ 3,628,800</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 3628800 결과: 10</p>
  <p>- n: 7 결과: 3</p>
  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>최대 팩토리얼인 10까지 반복문 돌리기</li>
      <li>res 와 i값을 곱하면서 i 팩토리얼 값 구하기</li>
      <li>res값이 n보다 같거나 작으면 answer 에 i값 저장하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(n) {
    var answer = 0;
    let res = 1;
    for(let i = 1; i<=10; i++){  
        res *= i;
        if(res <= n) answer = i;
    }
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="가까운수"> #가까운수</a>
  <h3>
    Q. 정수 배열 array와 정수 n이 매개변수로 주어질 때, array에 들어있는 정수 중
    n과 가장 가까운 수를 return 하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- 1 ≤ array의 길이 ≤ 100</p>
  <p>- 1 ≤ array의 원소 ≤ 100</p>
  <p>- 1 ≤ n ≤ 100</p>
  <p>- 가장 가까운 수가 여러 개일 경우 더 작은 수를 return 합니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- array: [3, 10, 28] n: 20 결과: 28</p>
  <p>- array: [10, 11, 12] n: 13 결과: 12</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>array를 map 돌면서 v를 뺏을 때의 절대값 구하기</li>
      <li>Math.min(...arr)를 사용해서 가장 작은 차이 구하기</li>
      <li>array -v의 값이 min이랑 같은 것들만 필터링하고, 오름차순 정렬하기</li>
      <li>가장 앞의 인덱스만 반환하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(array, n) {
    const arr = array.map((v)=>Math.abs(n-v))
    const min = Math.min(...arr)
    const minArr = array.filter((v)=> Math.abs(n-v) === min).sort()
    
    return minArr[0];
}
    </code>
  </pre>
</section>
<section>
  <a name="모음제거"> #모음제거</a>
  <h3>
    Q. 영어에선 a, e, i, o, u 다섯 가지 알파벳을 모음으로 분류합니다. 문자열
    my_string이 매개변수로 주어질 때 모음을 제거한 문자열을 return하도록
    solution 함수를 완성해주세요.
  </h3>
  <p>- my_string은 소문자와 공백으로 이루어져 있습니다.</p>
  <p>- 1 ≤ my_string의 길이 ≤ 1,000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_string: "bus" 결과: "bs"</p>
  <p>- my_string: "nice to meet you" 결과: "nc t mt y"</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>replace()와 정규 표현식을 사용하여 모음 aeiou를 ''으로 바꾸기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(my_string) {

  return my_string.replace(/[aeiou]/g, '');
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>my_string을 배열로 변환하고, 모음이 포함되어있지 않은 것들만 필터링</li>
    <li>모음이 제거된 배열 문자열으로 변환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(my_string) {
    return Array.from(my_string).filter(t => !['a', 'e', 'i', 'o', 'u'].includes(t)).join('');
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
