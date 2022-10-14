<li><a href="#주사위개수">주사위개수</a></li>
<li><a href="#중복된문자제거">중복된문자제거</a></li>
<li><a href="#최댓값만들기2">최댓값만들기2</a></li>
<li><a href="#최댓값만들기2">최댓값만들기2</a></li>
<li><a href="#모음제거">모음제거</a></li>

```html
<section>
  <a name="주사위개수"> #주사위개수</a>
  <h3>
    Q. 머쓱이는 직육면체 모양의 상자를 하나 가지고 있는데 이 상자에 정육면체
    모양의 주사위를 최대한 많이 채우고 싶습니다. 상자의 가로, 세로, 높이가
    저장되어있는 배열 box와 주사위 모서리의 길이 정수 n이 매개변수로 주어졌을
    때, 상자에 들어갈 수 있는 주사위의 최대 개수를 return 하도록 solution 함수를
    완성해주세요.
  </h3>
  <p>- box의 길이는 3입니다.</p>
  <p>- box[0] = 상자의 가로 길이</p>
  <p>- box[1] = 상자의 세로 길이</p>
  <p>- box[2] = 상자의 높이 길이</p>
  <p>- 1 ≤ box의 원소 ≤ 100</p>
  <p>- 1 ≤ n ≤ 50</p>
  <p>- n ≤ box의 원소</p>
  <p>- 주사위는 상자와 평행하게 넣습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- box: [1, 1, 1] n: 1 결과: 1</p>
  <p>- box: [10, 8, 6] n: 3 = 결과: 12</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>각 길이를 n으로 나누고 곱하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(box, n) {
    var answer = 1;
    box.map((a)=>answer *= parseInt(a /n))
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>구조분해</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(box, n) {
    let [width, length, height] = box;

    return Math.floor(width / n) * Math.floor(length / n) * Math.floor(height / n);
}
  </code>
</pre>
</section>
<section>
  <a name="중복된문자제거"> #중복된문자제거</a>
  <h3>
    Q. 문자열 my_string이 매개변수로 주어집니다. my_string에서 중복된 문자를
    제거하고 하나의 문자만 남긴 문자열을 return하도록 solution 함수를
    완성해주세요.
  </h3>
  <p>- 1 ≤ my_string ≤ 1,000</p>
  <p>- 대문자와 소문자를 구분합니다.</p>
  <p>- 공백(" ")도 하나의 문자로 구분합니다.</p>
  <p>- 중복된 문자 중 가장 앞에 있는 문자를 남깁니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_string : "people" 결과: "peol"</p>
  <p>- my_string : "We are the world" = 결과: "We arthwold"</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>new Set() 을 이용하여 중복제거</li>
      <li>[...new Set(my_string)] 코드 단축 가능</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(my_string) {
    var answer = '';
    const setNew = new Set([...my_string])
    answer = [...setNew].join('')
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="최댓값만들기2"> #최댓값만들기2</a>
  <h3>
    Q. 정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소 중 두 개를 곱해
    만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- -10,000 ≤ numbers의 원소 ≤ 10,000</p>
  <p>- 2 ≤ numbers 의 길이 ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- numbers: [1, 2, -3, 4, -5] 결과: 15</p>
  <p>- numbers: [0, -31, 24, 10, 1, 9] = 결과: 240</p>
  <p>- numbers: [10, 20, 30, 5, 5, 20, 5] = 결과: 600</p>
  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>numbers 오름차순으로 정렬</li>
      <li>가장 낮은 수 2개 곱한 값과 가장 높은 수 2개를 곱한 결과를 비교</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(numbers) {
    var answer = 0;
    const sortArr = numbers.sort((a,b)=>a-b);
    answer = Math.max(sortArr[0] * sortArr[1] , sortArr[numbers.length - 1] *sortArr[numbers.length - 2])
    
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="피자나눠먹기2"> #피자나눠먹기2</a>
  <h3>
    Q. 머쓱이네 피자가게는 피자를 여섯 조각으로 잘라 줍니다. 피자를 나눠먹을
    사람의 수 n이 매개변수로 주어질 때, n명이 주문한 피자를 남기지 않고 모두
    같은 수의 피자 조각을 먹어야 한다면 최소 몇 판을 시켜야 하는지를 return
    하도록 solution 함수를 완성해보세요.
  </h3>
  <p>- 1 ≤ n ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 6 결과: 1</p>
  <p>- n: 10 결과: 5</p>
  <p>- n: 4 결과: 2</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>
        사람수 * 1인당 먹을 수 있는 피자조각을 6으로 나눴을 때 0이 될때까지
        반복문 돌리기
      </li>
      <li>
        사람수 * 1인당 먹을 수 있는 피자조각을 6으로 나눴을 때 몫 반환
        (피자판수)
      </li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(n) {
    var answer = 0;
    let count = 1;
    while(n * count % 6 != 0){
        count += 1
    }
    answer = count * n / 6
    
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>
      피자판 * 6(조각) 을 사람수로 나눈 나머지가 0이 될때까지 반복문 돌리기
    </li>
    <li>피자판수 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(n) {
    let pizza = 1;
    while (pizza * 6 % n) {
        pizza++;
    }
    return pizza;
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
