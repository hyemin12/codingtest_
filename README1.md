<li><a href="#외계행성의나이">외계행성의나이</a></li>
<li><a href="#7의개수">7의개수</a></li>
<li><a href="#인덱스바꾸기">인덱스바꾸기</a></li>
<li><a href="#개미군단">개미군단</a></li>
<li><a href="#숫자찾기">숫자찾기</a></li>

```html
<section>
  <a name="외계행성의나이"> #외계행성의나이</a>
  <h3>
    Q. 우주여행을 하던 머쓱이는 엔진 고장으로 PROGRAMMERS-962 행성에 불시착하게
    됐습니다. 입국심사에서 나이를 말해야 하는데, PROGRAMMERS-962 행성에서는
    나이를 알파벳으로 말하고 있습니다. a는 0, b는 1, c는 2, ..., j는 9입니다.
    예를 들어 23살은 cd, 51살은 fb로 표현합니다. 나이 age가 매개변수로 주어질 때
    PROGRAMMER-962식 나이를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- age는 자연수입니다.</p>
  <p>- age ≤ 1,000</p>
  <p>- PROGRAMMERS-962 행성은 알파벳 소문자만 사용합니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- age: 23 결과: "cd"</p>
  <p>- age: 51 = 결과: "fb"</p>
  <p>- age: 100 = 결과: "baa"</p>
  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>영어단어를 배열</li>
      <li>age 배열로 변환해서 반복문 돌리기</li>
      <li>영어 배열의 index값을 추가하기</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(age) {
    var answer = '';

    const engArr = 'abcdefghij'
    const arr = age.toString().split('')
    
    for(let i = 0; i < arr.length;i++){
        answer += engArr[arr[i]]
    }
    
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="7의개수"> #7의개수</a>
  <h3>
    Q. 머쓱이는 행운의 숫자 7을 가장 좋아합니다. 정수 배열 array가 매개변수로
    주어질 때, 7이 총 몇 개 있는지 return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>- 1 ≤ array의 길이 ≤ 100</p>
  <p>- 0 ≤ array의 원소 ≤ 100,000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- array: [7, 77, 17] 결과: 4</p>
  <p>- array: [10, 29] = 결과: 0</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>array 숫자 한자리수로 배열 변환</li>
      <li>반복문 돌면서 7인 배열만 반환</li>
      <li>길이 출력</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(array) {
    var answer = 0;
    const arr = array.toString().split('')
    answer = arr.filter((v)=>v === '7').length

    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>배열을 하나로 합치기</li>
    <li>7을 기준으로 나누기</li>
    <li>길이 -1 출력</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(array) {
    return array.join('').split('7').length-1;
}
  </code>
</pre>
</section>
<section>
  <a name="인덱스바꾸기"> #인덱스바꾸기</a>
  <h3>
    Q. 문자열 my_string과 정수 num1, num2가 매개변수로 주어질 때, my_string에서
    인덱스 num1과 인덱스 num2에 해당하는 문자를 바꾼 문자열을 return 하도록
    solution 함수를 완성해보세요.
  </h3>
  <p>- 1 < my_string의 길이 < 100</p>
  <p>- 0 ≤ num1, num2 < my_string의 길이</p>
  <p>- my_string은 소문자로 이루어져 있습니다.</p>
  <p>- num1 ≠ num2</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_string: "hello" num1: 1 num2: 2 결과: "hlelo"</p>
  <p>- my_string: "I love you" num1: 3 num2: 6 = 결과: "I l veoyou"</p>
  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>인덱스가 num1이랑 같으면 num2인덱스로 변경</li>
      <li>인덱스가 num2이랑 같으면 num1인덱스로 변경</li>
      <li>둘 다 아닐경우 answer에 my_string문자열 추가</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(my_string, num1, num2) {
    var answer = '';
    
    for(let i =0;i＜my_string.length;i++){
        if(i == num1) {
          answer += my_string[num2]
        } else if(i == num2) {
          answer += my_string[num1]
          } else{answer += my_string[i]
        }
    }
    
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>my_string을 배열로 변환</li>
    <li>num1, num2 내용 바꾸기</li>
    <li>배열 문자열로 변환하기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(my_string, num1, num2) {
    my_string = my_string.split('');
    [my_string[num1], my_string[num2]] = [my_string[num2], my_string[num1]];
    
    return my_string.join('');
}

  </code>
</pre>
</section>
<section>
  <a name="개미군단"> #개미군단</a>
  <h3>
    Q. 개미 군단이 사냥을 나가려고 합니다. 개미군단은 사냥감의 체력에 딱 맞는
    병력을 데리고 나가려고 합니다. 장군개미는 5의 공격력을, 병정개미는 3의
    공격력을 일개미는 1의 공격력을 가지고 있습니다. 예를 들어 체력 23의 여치를
    사냥하려고 할 때, 일개미 23마리를 데리고 가도 되지만, 장군개미 네 마리와
    병정개미 한 마리를 데리고 간다면 더 적은 병력으로 사냥할 수 있습니다.
    사냥감의 체력 hp가 매개변수로 주어질 때, 사냥감의 체력에 딱 맞게 최소한의
    병력을 구성하려면 몇 마리의 개미가 필요한지를 return하도록 solution 함수를
    완성해주세요.
  </h3>
  <p>- hp는 자연수입니다.</p>
  <p>- 0 ≤ hp ≤ 1000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- hp: 23 결과: 5</p>
  <p>- hp: 24 결과: 6</p>
  <p>- hp: 999 결과: 201</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>hp를 5로 나눈 몫을 count1에 저장</li>
      <li>
        hp에서 5로 나눈 값을 빼고, 3으로 나눈 몫을 count2에 저장(hp - count1 *
        5)
      </li>
      <li>hp에서 5로 나눈 값, 3으로 나눈 값 빼고 난 나머지 count3에 저장</li>
      <li>answer = count1 + count2 + count3</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(hp) {
    var answer = 0;
    const count1 = Math.floor(hp / 5)
    const count2 = Math.floor((hp - count1 * 5) / 3)
    const count3 = hp - (count1 * 5) - (count2 * 3)
    answer = count1 + count2 + count3
    return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>hp를 5로 나눈 몫을 cnt에 더하기</li>
    <li>hp를 5로 나눈 나머지로 저장</li>
    <li>hp를 3로 나눈 몫을 cnt에 더하기</li>
    <li>hp를 3로 나눈 나머지로 저장</li>
    <li>hp가 없으면 cnt 리턴</li>
    <li>hp를 1로 나눈 몫을 cnt에 더하기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(hp) {
    let cnt = 0;
    cnt += Math.floor(hp / 5);
    hp %= 5;
    if (!hp) return cnt;
    cnt += Math.floor(hp / 3);
    hp %= 3;
    if (!hp) return cnt;
    cnt += Math.floor(hp / 1);
    return cnt;
}
  </code>
</pre>
</section>
<section>
  <a name="숫자찾기"> #숫자찾기</a>
  <h3>
    Q. 정수 num과 k가 매개변수로 주어질 때, num을 이루는 숫자 중에 k가 있으면
    num의 그 숫자가 있는 자리 수를 return하고 없으면 -1을 return 하도록 solution
    함수를 완성해보세요.
  </h3>
  <p>- 0 < num < 1,000,000</p>
  <p>- 0 ≤ k < 10</p>
  <p>- num에 k가 여러 개 있으면 가장 처음 나타나는 자리를 return 합니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- num: 29183 k: 1 결과: 3</p>
  <p>- num: 232443 k: 4 결과: 4</p>
  <p>- num: 123456 k: 7 결과: -1</p>

  <div style="margin-top: 15px; padding: 10px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>hp를 5로 나눈 몫을 count1에 저장</li>
      <li>
        hp에서 5로 나눈 값을 빼고, 3으로 나눈 몫을 count2에 저장(hp - count1 *
        5)
      </li>
      <li>hp에서 5로 나눈 값, 3으로 나눈 값 빼고 난 나머지 count3에 저장</li>
      <li>answer = count1 + count2 + count3</li>
    </ol>
  </div>
  <pre>
    <code class="javascript">   
function solution(num, k) {
    var answer = 0;
    const index = num.toString().indexOf(k)
    answer = index == -1 ? -1 : index + 1
    
    return answer;
}
    </code>
  </pre>
</section>
```

function solution(my_string, num1, num2) {
my_string = my_string.split('');
[my_string[num1], my_string[num2]] = [my_string[num2], my_string[num1]];
return my_string.join('');
}

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
