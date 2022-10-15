<li><a href="#A로B만들기">A로B만들기</a></li>
<li><a href="#2차원으로만들기">2차원으로만들기 </a></li>
<li><a href="#잘라서배열로저장">잘라서배열로저장</a></li>
<li><a href="#종이자르기">종이자르기</a></li>
<li><a href="#모음제거">모음제거</a></li>

```html
<section>
  <a name="A로B만들기"> #A로B만들기</a>
  <h3>
    Q. 문자열 before와 after가 매개변수로 주어질 때, before의 순서를 바꾸어
    after를 만들 수 있으면 1을, 만들 수 없으면 0을 return 하도록 solution 함수를
    완성해보세요.
  </h3>
  <p>- 0 < before의 길이 == after의 길이 < 1,000</p>
  <p>- before와 after는 모두 소문자로 이루어져 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- before: "olleh" after: "hello" 결과: 1</p>
  <p>- before: "allpe" after: "apple" 결과: 0</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>after와 before 모두 배열로 바꾼 뒤 정렬하고</li>
      <li>after 맵 돌면서 같은지 비교</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(before, after) {
    var answer = 0;
    const sortB= before.split('').sort((a,b)=>(a＜b)?1:-1)
    const sortA= after.split('').sort((a,b)=>(a＜b)?1:-1)
    const result = sortA.filter((a,i)=>a !== sortB[i])
    
    answer = result.length === 0 ? 1 : 0
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>before과 after를 배열로 변환 -> 정렬 -> 문자열 후 비교</li>
    <li>같으면 1 반환 아니면 0 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(before, after) {
    return before.split('').sort().join('') === after.split('').sort().join('') ? 1 : 0;
}
  </code>
</pre>
</section>
<section>
  <a name="2차원으로만들기"> #2차원으로만들기</a>
  <h3>
    Q. 정수 배열 num_list와 정수 n이 매개변수로 주어집니다. num_list를 다음
    설명과 같이 2차원 배열로 바꿔 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    num_list가 [1, 2, 3, 4, 5, 6, 7, 8] 로 길이가 8이고 n이 2이므로 num_list를 2
    * 4 배열로 다음과 같이 변경합니다. 2차원으로 바꿀 때에는 num_list의 원소들을
    앞에서부터 n개씩 나눠 2차원 배열로 변경합니다.
  </p>
  <p>- num_list : [1, 2, 3, 4, 5, 6, 7, 8] / n: 2</p>
  <p>- 결과: [[1, 2], [3, 4], [5, 6], [7, 8]]</p>
  <br />
  <p>- num_list의 길이는 n의 배 수개입니다.</p>
  <p>- 0 ≤ num_list의 길이 ≤ 1000</p>
  <p>- 2 ≤ n < num_list의 길이</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>
    - num_list : [1, 2, 3, 4, 5, 6, 7, 8] n: 2 결과: [[1, 2], [3, 4], [5, 6],
    [7, 8]]
  </p>
  <p>
    - num_list : [100, 95, 2, 4, 5, 6, 18, 33, 948] n: 3 = 결과: [[100, 95, 2],
    [4, 5, 6], [18, 33, 948]]
  </p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>0부터 n번까지 인덱스를 잘라서, answer에 집어넣기</li>
      <li>배열의 길이를 n으로 나눈 값까지 반복</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(num_list, n) {
    var answer = [];
    for(let i =0;i＜num_list.length / n; i++){
        const idx = i * n
        let arr = num_list.slice(idx,idx + n)
        answer.push(arr)
    }
    return answer;
}
    </code></pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>i 증감값을 i + n으로 해서, 가독성을 높임</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(num_list, n) {
    var answer = [];

    for (let i = 0; i＜num_list.length; i=i+n){
        answer.push(num_list.slice(i, i+n));
    }

    return answer;
}
  </code>
</pre>
</section>
<section>
  <a name="잘라서배열로저장"> #잘라서배열로저장</a>
  <h3>
    Q. 문자열 my_str과 n이 매개변수로 주어질 때, my_str을 길이 n씩 잘라서 저장한
    배열을 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- 1 ≤ my_str의 길이 ≤ 100</p>
  <p>- 1 ≤ n ≤ my_str의 길이</p>
  <p>- my_str은 알파벳 소문자, 대문자, 숫자로 이루어져 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_str: "abc1Addfggg4556b" n: 6 결과: ["abc1Ad", "dfggg4", "556b"]</p>
  <p>- my_str: "abcdef123" n: 3 = 결과: ["abc", "def", "123"]</p>
  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>my_str의 0번부터 n+i번까지 잘라서 answer에 넣기</li>
      <li>증감값 : i+=n</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(my_str, n) {
    var answer = [];
    for(let i =0;i＜my_str.length ;i+=n){
        const arr = my_str.slice(i,n+i)
        answer.push(arr)
    }
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="종이자르기"> #종이자르기</a>
  <h3>
    Q. 머쓱이는 큰 종이를 1 x 1 크기로 자르려고 합니다. 예를 들어 2 x 2 크기의
    종이를 1 x 1 크기로 자르려면 최소 가위질 세 번이 필요합니다.
    <br />
    정수 M, N이 매개변수로 주어질 때, M x N 크기의 종이를 최소로 가위질 해야하는
    횟수를 return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>- 0 < M, N < 100</p>
  <p>- 종이를 겹쳐서 자를 수 없습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- M: 2 N: 2 결과: 3</p>
  <p>- M: 2 N: 5 결과: 9</p>
  <p>- M: 1 N: 1 결과: 0</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>M : M - 1 (길이보다 1 작은 수로 자를 수 있기 때문에)</li>
      <li>N : N - 1 * M (세로를 자른 개수 * 가로의 길이)</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(M, N) {
    var answer = 0;
    answer += M - 1 + (N - 1) * M
    
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>가로길이 * 세로길이 - 1</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(M, N) {
    return M*N-1;
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
