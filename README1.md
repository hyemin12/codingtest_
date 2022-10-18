<li><a href="#문자열밀기">문자열밀기</a></li>
<li><a href="#외계어사전">외계어사전</a></li>
<li><a href="#진료순서정하기">진료순서정하기</a></li>
<li><a href="#숨어있는숫자의덧셈2">숨어있는숫자의덧셈2</a></li>

```html
<section>
  <a name="문자열밀기"> #문자열밀기</a>
  <h3>
    Q. 문자열 "hello"에서 각 문자를 오른쪽으로 한 칸씩 밀고 마지막 문자는 맨
    앞으로 이동시키면 "ohell"이 됩니다. 이것을 문자열을 민다고 정의한다면 문자열
    A와 B가 매개변수로 주어질 때, A를 밀어서 B가 될 수 있다면 몇 번 밀어야
    하는지 횟수를 return하고 밀어서 B가 될 수 없으면 -1을 return 하도록 solution
    함수를 완성해보세요.
  </h3>
  <p>- 0 < A의 길이 = B의 길이 < 100</p>
  <p>- A, B는 알파벳 소문자로 이루어져 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- A: "hello" B: "ohell" 결과: 1</p>
  <p>- A: "apple" B: "elppa" 결과: -1</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>answer = -1 (초기값)</li>
      <li>A와 B가 같으면 answer = 0</li>
      <li>A와 B가 다르면</li>
      <li>
        A 문자열을 뒤에서부터 i번 자른 값과 앞에서부터 0 ~ i번까지 자른 값을
        구해서 (sliceA)
      </li>
      <li>sliceA와 B 문자열 비교하고, answer에 i 할당</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(A, B) {
    var answer = -1;
    
    for(let i = 1; i＜A.length ;i++){
        if(A !== B){
            const sliceA = A.slice(-i) + A.slice(0,-i) 
            sliceA === B ? answer = i : ''
        } else {
            answer = 0
        } 
    }
    
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>문자열 B + B 하고, A의 인덱스값 찾기..</li>
    <li>Eg. B + B = ohellohell</li>
    <li>"ohellohell".indexOf("hello")</li>
    <li>결과 : 1</li>
  </ul>

  <pre>
  <code class="javascript">
let solution=(a,b)=>(b+b).indexOf(a)
  </code>
</pre>
</section>
<section>
  <a name="외계어사전"> #외계어사전</a>
  <h3>
    Q. PROGRAMMERS-962 행성에 불시착한 우주비행사 머쓱이는 외계행성의 언어를
    공부하려고 합니다. 알파벳이 담긴 배열 spell과 외계어 사전 dic이 매개변수로
    주어집니다. spell에 담긴 알파벳을 한번씩만 모두 사용한 단어가 dic에
    존재한다면 1, 존재하지 않는다면 2를 return하도록 solution 함수를
    완성해주세요.
  </h3>
  <p>- spell과 dic의 원소는 알파벳 소문자로만 이루어져있습니다.</p>
  <p>- 2 ≤ spell의 크기 ≤ 10</p>
  <p>- spell의 원소의 길이는 1입니다.</p>
  <p>- 1 ≤ dic의 크기 ≤ 10</p>
  <p>- 1 ≤ dic의 원소의 길이 ≤ 10</p>
  <p>- spell의 원소를 모두 사용해 단어를 만들어야 합니다.</p>
  <p>
    - spell의 원소를 모두 사용해 만들 수 있는 단어는 dic에 두 개 이상 존재하지
    않습니다.
  </p>
  <p>- dic과 spell 모두 중복된 원소를 갖지 않습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>
    - spell: ["p", "o", "s"] dic: ["sod", "eocd", "qixm", "adio", "soo"] 결과: 2
  </p>
  <p>- spell: ["z", "d", "x"] dic: ["def", "dww", "dzx", "loveaw"] 결과: 1</p>
  <p>
    - spell: ["s", "o", "m", "d"] dic: ["moos", "dzx", "smm", "sunmmo", "som"]
    결과: 2
  </p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>answer = 2</li>
      <li>spell을 오름차순으로 정렬</li>
      <li>dic 길이만큼 반복하는 반복문 작성</li>
      <li>dic[i]을 배열로 변환 후 오름차순으로 정렬하고, 문자열으로 반환</li>
      <li>sortedSpell와 sortedDic가 같으면 answer = 1로 저장</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(spell, dic) {
    var answer = 2;
    const sortedSpell = spell.sort((a,b)=>(a＜b)?-1:1).join('')
    
    for(let i =0 ;i＜dic.length;i++){
        const sortedDic = dic[i].split('').sort((a,b)=>(a＜b)?-1:1).join('')
        sortedSpell === sortedDic ? answer = 1 : ''
    }
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="진료순서정하기"> #진료순서정하기</a>
  <h3>
    Q. 외과의사 머쓱이는 응급실에 온 환자의 응급도를 기준으로 진료 순서를
    정하려고 합니다. 정수 배열 emergency가 매개변수로 주어질 때 응급도가 높은
    순서대로 진료 순서를 정한 배열을 return하도록 solution 함수를 완성해주세요.
  </h3>

  <p>- 중복된 원소는 없습니다.</p>
  <p>- 1 ≤ emergency의 길이 ≤ 10</p>
  <p>- 1 ≤ emergency의 원소 ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- emergency: [3, 76, 24] = 결과: [3, 1, 2]</p>
  <p>- emergency: [1, 2, 3, 4, 5, 6, 7] = 결과: [7, 6, 5, 4, 3, 2, 1]</p>
  <p>- emergency: [30, 10, 23, 6, 100] = 결과: [2, 4, 3, 5, 1]</p>

  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>emergency을 내림차순으로 정렬하고, 변수에 저장</li>
      <li>emergency을 map돌면서 정렬한 배열의 index값으로 바꾸기</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(emergency) {
    var answer = [];
    const sortedArr = [...emergency].sort((a,b)=>b-a)
    answer = emergency.map((a) => a = sortedArr.indexOf(a) + 1)
    return answer;
}
  </code>
</pre>
</section>
<section>
  <a name="숨어있는숫자의덧셈2"> #숨어있는숫자의덧셈2</a>
  <h3>
    Q. 문자열 my_string이 매개변수로 주어집니다. my_string은 소문자, 대문자,
    자연수로만 구성되어있습니다. my_string안의 자연수들의 합을 return하도록
    solution 함수를 완성해주세요.
  </h3>

  <p>- 1 ≤ my_string의 길이 ≤ 1,000</p>
  <p>- 1 ≤ my_string 안의 자연수 ≤ 1000</p>
  <p>- 연속된 수는 하나의 숫자로 간주합니다.</p>
  <p>- 000123과 같이 0이 선행하는 경우는 없습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_string: "aAb1B2cC34oOp" = 결과: 37</p>
  <p>- my_string: "1a2b3c4d123Z" = 결과: 133</p>

  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>
        my_string을 숫자를 제외한 문자를 기준으로 나누기 (split(/[^0-9]/))
      </li>
      <li>배열을 map돌면서 공백이 아닐경우 answer에 더하기</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(my_string) {
    var answer = 0;
    my_string.split(/[^0-9]/).map((v)=> v !== '' ? answer += parseInt(v): '')
    return answer;
}
  </code>
</pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>[^0-9] == /\D+/</li>
    <li>reduce로 결과값 구하기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(my_string) {
  return my_string.split(/\D+/).reduce((acc, cur) => acc + Number(cur), 0);
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

  <p>- A에서 첫번째 숫</p>

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

  </code>
</pre>
</section>
```
