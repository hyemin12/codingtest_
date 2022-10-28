<li><a href="#다항식더하기">다항식더하기</a></li>

```html

```

```html
<section>
  <a name="다항식더하기"> #다항식더하기</a>
  <h3>
    Q. 한 개 이상의 항의 합으로 이루어진 식을 다항식이라고 합니다. 다항식을
    계산할 때는 동류항끼리 계산해 정리합니다. 덧셈으로 이루어진 다항식
    polynomial이 매개변수로 주어질 때, 동류항끼리 더한 결괏값을 문자열로 return
    하도록 solution 함수를 완성해보세요. 같은 식이라면 가장 짧은 수식을 return
    합니다.
  </h3>

  <p>- 0 < polynomial에 있는 수 < 100</p>
  <p>- polynomial에 변수는 'x'만 존재합니다.</p>
  <p>- polynomial은 0부터 9까지의 정수, 공백, ‘x’, ‘+'로 이루어져 있습니다.</p>
  <p>- 항과 연산기호 사이에는 항상 공백이 존재합니다.</p>
  <p>- 공백은 연속되지 않으며 시작이나 끝에는 공백이 없습니다.</p>
  <p>- 하나의 항에서 변수가 숫자 앞에 오는 경우는 없습니다.</p>
  <p>- " + 3xx + + x7 + "와 같은 잘못된 입력은 주어지지 않습니다.</p>
  <p>- "012x + 001"처럼 0을 제외하고는 0으로 시작하는 수는 없습니다.</p>
  <p>- 문자와 숫자 사이의 곱하기는 생략합니다.</p>
  <p>- polynomial에는 일차 항과 상수항만 존재합니다.</p>
  <p>- 계수 1은 생략합니다.</p>
  <p>- 결괏값에 상수항은 마지막에 둡니다.</p>
  <p>- 0 < polynomial의 길이 < 50</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- polynomial: "3x + 7 + x" = 결과: "4x + 7"</p>
  <p>- polynomial: "x + x + x" = 결과: "3x"</p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>주어진 문자열 더하기를 기준으로 나누고 배열로 변환하기</li>
      <li>x가 포함된 배열만, 필터링해서 xArr에 저장하기</li>
      <li>
        xArr 맵돌면서 x일 경우에는 1만 반환, 아닐 경우에는 x를 없애고 숫자만
        반환
      </li>
      <li>x 값 모두 더해서 xCount에 저장하기</li>
      <li>배열에 x가 포함되지 않은 수만 필터링해서 numArr에 저장하기</li>
      <li>
        numArr의 길이가 1이면 첫번째 인덱스값 반환, 아닐 경우에는 숫자만 모두
        더한 값 저장
      </li>
      <li>x = countX 가 0보다 작으면 빈 문자열 반환</li>
      <li>countX가 1보다 큰 경우에는 countX 반환, 1인경우에는 빈문자열 반환</li>
      <li>num = countNum이 0보다 크면 countNum 반환 아닐경우 빈 문자열 반환</li>
      <li>plus = x가 빈 문자열이 아니고, num도 빈 문자열이 아닐 경우 반환</li>
      <li>x + plus + num 반환</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(polynomial) {
    const arr = polynomial.split(' + ')
    
    // x값 계산
    const xArr = arr.filter((v)=>v.includes('x'))
    if(xArr.length > 0){
        var countX = xArr.map((a)=> a === 'x' ? '1': a.replace('x','')).reduce((acc,cur) => acc*1 + cur*1)
     }
    
    // 숫자 계산
    const numArr = arr.filter((v)=> !v.includes('x'))
    if(numArr.length>0){
      var countNum =  numArr.length === 1 ? Number(numArr[0]) : numArr.reduce((acc,cur)=> acc*1 + cur*1)
    }
  
   const x = countX > 0 ? `${countX > 1 ? countX : ''}x` : '';
   const num = countNum > 0 ? countNum : '';
   const plus = x !== '' && num !== '' ? ' + ' : '';
                
    return x + plus + num;
}
  </code>
</pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>
      문자열을 공백을 기준으로 나누고, +가 아닌 값만 필터링 하기 (연산제외
      숫자값 배열)
    </li>
    <li>x = x만 가진 문자열을 필터링 하고, 맵돌면서 숫자값 반환하기</li>
    <li>n = x를 가지지 않은 문자열만 필터링하고, 숫자값 반환하기</li>
    <li>x값, n값 더해서 ans 배열에 집어넣기</li>
    <li>ans[0]이 1x라면 x 값으로 재할당</li>
    <li>ans 배열 ' + '을 기준으로 합치기</li>
    <li>배열의 값이 하나라면 값만 리턴, ' + '을 기준으로 합칠 것이 없기때문</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(polynomial) {
    let p = polynomial.split(' ').filter(v=>v!=='+');
    let x = p.filter(v=>v[v.length-1] === 'x').map(v=>v.length === 1 ? 1 : +(v.slice(0, -1))),
        n = p.filter(v=>v[v.length-1] !== 'x').map(v=>+v);

    let ans = [];
    if (x.length) ans.push(x.reduce((a,v)=>a+v)+'x');
    if (n.length) ans.push(n.reduce((a,v)=>a+v)+'');

    if (ans[0] === '1x') ans[0] = 'x';

    return ans.join(' + ');
}
  </code>
</pre>
</section>
```
