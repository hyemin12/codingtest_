<li><a href="#문자열계산하기">문자열계산하기</a></li>
<li><a href="#외계어사전">외계어사전</a></li>
<li><a href="#진료순서정하기">진료순서정하기</a></li>
<li><a href="#숨어있는숫자의덧셈2">숨어있는숫자의덧셈2</a></li>

```html
<section>
  <a name="문자열밀기"> #문자열밀기</a>
  <h3>
    Q. my_string은 "3 + 5"처럼 문자열로 된 수식입니다. 문자열 my_string이
    매개변수로 주어질 때, 수식을 계산한 값을 return 하는 solution 함수를
    완성해주세요.
  </h3>
  <p>- 연산자는 +, -만 존재합니다.</p>
  <p>- 문자열의 시작과 끝에는 공백이 없습니다.</p>
  <p>- 0으로 시작하는 숫자는 주어지지 않습니다.</p>
  <p>- 잘못된 수식은 주어지지 않습니다.</p>
  <p>- 5 ≤ my_string의 길이 ≤ 100</p>
  <p>- my_string을 계산한 결과값은 1 이상 100,000 이하입니다.</p>
  <p>- my_string의 중간 계산 값은 -100,000 이상 100,000 이하입니다.</p>
  <p>- 계산에 사용하는 숫자는 1 이상 20,000 이하인 자연수입니다.</p>
  <p>- my_string에는 연산자가 적어도 하나 포함되어 있습니다.</p>
  <p>- return type 은 정수형입니다.</p>
  <p>- my_string의 숫자와 연산자는 공백 하나로 구분되어 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_string: "3 + 4" 결과: 7</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>my_string을 공백을 기준으로 배열로 변환</li>
      <li>answer 초기값을 배열의 0번째 인덱스로 설정</li>
      <li>arr.length-1 만큼 반복문 작성</li>
      <li>if(arr[i+1] === '+'), 부호 다음 인덱스의 값을 answer에 더하기</li>
      <li>if(arr[i+1] === '-'), 부호 다음 인덱스의 값을 answer에 빼기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(my_string) {
    const arr = my_string.split(' ');
    var answer = arr[0] *1;
    for(let i = 0; i＜arr.length-1; i+=2 ){
        if(arr[i+1] === '+') answer += arr[i+2] *1 
        if(arr[i+1] === '-') answer -= arr[i+2] *1 
    }
    
    return answer;
}
    
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>eval()로 문자로 표현된 JavaScript 코드를 실행</li>
    <li>※ 문자열로부터 **eval()**을 실행하는 것은 엄청나게 위험</li>
    <li>※ 해커가 위험한 코드를 사용할 수 있음</li>
  </ul>

  <pre>
  <code class="javascript">
function solution(my_string) {
    return eval(my_string);
}
  </code>
</pre>
</section>
<section>
  <a name="다음에올숫자"> #다음에올숫자</a>
  <h3>
    Q. 등차수열 혹은 등비수열 common이 매개변수로 주어질 때, 마지막 원소
    다음으로 올 숫자를 return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>- 2 < common의 길이 < 1,000</p>
  <p>- -1,000 < common의 원소 < 2,000</p>
  <p>- 등차수열 혹은 등비수열이 아닌 경우는 없습니다.</p>
  <p>- 공비가 0인 경우는 없습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- common: [1, 2, 3, 4] 결과: 5</p>
  <p>- common: [2, 4, 8] 결과: 16</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>등차수열인지 조건문 작성</li>
      <li>2번째 인덱스 - 1번째 인덱스 === 1번째 인덱스 - 0번째 인덱스</li>
      <li>조건이 true일 경우 마지막 숫자 + 공차 숫자</li>
      <li>
        조건이 false 경우 마지막 숫자 + 공비 숫자(commin[1]을 commin[0]으로 나눈
        몫)
      </li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(common) {
    var answer = 0;
    const isAdd = common[1] - common[0] === common[2] - common[1]
    answer = isAdd 
        ? common[common.length-1]+common[1]-common[0] 
        : common[common.length-1]*(common[1]/common[0])

    return answer
}
    </code>
  </pre>
</section>
<section>
  <a name="컨트롤제트"> #컨트롤제트</a>
  <h3>
    Q. 숫자들이 공백으로 구분된 문자열이 주어집니다. 문자열에 있는 숫자를
    차례대로 더하려고 합니다. 이 때 “Z”가 나오면 바로 전에 더했던 숫자를 뺀다는
    뜻입니다. 숫자와 “Z”로 이루어진 문자열 s가 주어질 때, 머쓱이가 구한 값을
    return 하도록 solution 함수를 완성해보세요.
  </h3>

  <p>- 0 < s의 길이 < 1,000</p>
  <p>- -1,000 < s의 원소 중 숫자 < 1,000</p>
  <p>- s는 숫자, "Z", 공백으로 이루어져 있습니다.</p>
  <p>- 연속된 공백은 주어지지 않습니다.</p>
  <p>- 0을 제외하고는 0으로 시작하는 숫자는 없습니다.</p>
  <p>- s의 시작과 끝에는 공백이 없습니다.</p>
  <p>- 모든 숫자를 지우는 경우는 주어지지 않습니다.</p>
  <p>- 지울 숫자가 없는 상태에서 "Z"는 무시합니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- emergency: [3, 76, 24] = 결과: [3, 1, 2]</p>
  <p>- emergency: [1, 2, 3, 4, 5, 6, 7] = 결과: [7, 6, 5, 4, 3, 2, 1]</p>
  <p>- emergency: [30, 10, 23, 6, 100] = 결과: [2, 4, 3, 5, 1]</p>

  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>emergency을 내림차순으로 정렬하고, 변수에 저장</li>
      <li>※ 테스트 2번 미통과.. 왜지?</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
const arr =  s.split(' ')
  for(let i = 0;i＜arr.length;i++){
      if(arr.includes('Z')) arr.splice(arr.indexOf('Z') - 1, 2)
  }
  answer = arr.map((v)=>v*1).reduce((acc,cur)=>acc+cur)
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
