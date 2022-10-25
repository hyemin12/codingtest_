<li><a href="#OX퀴즈">OX퀴즈</a></li>

```html

```

```html
<section>
  <a name="OX퀴즈"> #OX퀴즈</a>
  <h3>
    Q. 덧셈, 뺄셈 수식들이 'X [연산자] Y = Z' 형태로 들어있는 문자열 배열 quiz가
    매개변수로 주어집니다. 수식이 옳다면 "O"를 틀리다면 "X"를 순서대로 담은
    배열을 return하도록 solution 함수를 완성해주세요.
  </h3>

  <p>
    - 연산 기호와 숫자 사이는 항상 하나의 공백이 존재합니다. 단 음수를 표시하는
    마이너스 기호와 숫자 사이에는 공백이 존재하지 않습니다.
  </p>
  <p>- 1 ≤ quiz의 길이 ≤ 10</p>
  <p>
    - X, Y, Z는 각각 0부터 9까지 숫자로 이루어진 정수를 의미하며, 각 숫자의 맨
    앞에 마이너스 기호가 하나 있을 수 있고 이는 음수를 의미합니다.
  </p>
  <p>- X, Y, Z는 0을 제외하고는 0으로 시작하지 않습니다.</p>
  <p>- -10,000 ≤ X, Y ≤ 10,000</p>
  <p>- -20,000 ≤ Z ≤ 20,000</p>
  <p>- [연산자]는 + 와 - 중 하나입니다.</p>
  <br />

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- quiz: ["3 - 4 = -3", "5 + 6 = 11"] = 결과: ["X", "O"]</p>
  <p>
    - quiz: ["19 - 6 = 13", "5 + 66 = 71", "5 - 15 = 63", "3 - 1 = 2"] = 결과:
    ["O", "O", "X", "O"]
  </p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>quiz를 맵돌면서 문제와 정답을 나누기 ('='을 기준으로)</li>
      <li>quiz의 길이만큼 반복해서 실행</li>
      <li>문제의 정답을 담을 변수 result 선언</li>
      <li>// 주어진 문제 계산하기</li>
      <li>문제를 공백을 기준으로 나눠서 연산자[+ , -]구분하기</li>
      <li>연산자가 +면 0번째 인덱스 + 2번째 인덱스</li>
      <li>주어진 문제의 길이만큼 반복</li>
      <li>결과가 주어진 정답과 같으면 'O', 아니면 'X' 배열에 담기</li>
      <li>※ eval 사용 권장하지 않아 반복문으로 코드 작성</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(quiz) {
    var answer = [];
    const newArr = quiz.map((q)=>q.split('='))
    
    for(let i=0;i＜quiz.length;i++){
        let result = 0
        const calc = newArr[i][0].split(' ')
        
        for(let j =0; j＜newArr[i].length; j+=2){
            result = calc[j + 1] === '+' ? calc[j]*1 + calc[j+2]*1 : calc[j]*1 - calc[j+2]*1
        }
        result === parseInt(newArr[i][1]) ? answer.push('O') : answer.push('X')
    }
    
    return answer;
}
  </code>
</pre>

  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>quiz를 맵돌면서 문제와 정답을 나누기 ('='을 기준으로)</li>
    <li>계산식 => calc / 주어진 정답 => result</li>
    <li>sign = cal에 + 포함 여부 확인</li>
    <li>sign으로 연산자를 기준으로 나누기</li>
    <li>a + (b *sign) 값이 result와 같으면 'O', 아니면 'X' 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(quiz) {
    var answer = [];
    return quiz.map(t => {
        const [calc, result] = t.split(' = ');
        const sign = calc.includes('+') ? 1 : -1
        const [a, b] = calc.split(sign === 1 ? ' + ' : ' - ');

        return +a + (+b * sign) === +result ? 'O' : 'X'
    });
}
  </code>
</pre>
</section>
```
