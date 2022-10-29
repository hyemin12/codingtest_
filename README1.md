<li><a href="#연속된수의합">연속된수의합</a></li>

```html

```

```html
<section>
  <a name="연속된수의합"> #연속된수의합</a>
  <h3>
    Q. 연속된 세 개의 정수를 더해 12가 되는 경우는 3, 4, 5입니다. 두 정수 num과
    total이 주어집니다. 연속된 수 num개를 더한 값이 total이 될 때, 정수 배열을
    오름차순으로 담아 return하도록 solution함수를 완성해보세요.
  </h3>

  <p>- 1 ≤ num ≤ 100</p>
  <p>- 0 ≤ total ≤ 1000</p>
  <p>
    - num개의 연속된 수를 더하여 total이 될 수 없는 테스트 케이스는 없습니다.
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- num: 3 total: 12 = 결과: [3, 4, 5]</p>
  <p>- num: 5 total: 15 = 결과: [1, 2, 3, 4, 5]</p>
  <p>- num: 4 total: 14 = 결과: [2, 3, 4, 5]</p>
  <p>- num: 5 total: 5 = 결과: [-1, 0, 1, 2, 3]</p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>
        ※ for문을 작성해서 total 값을 만드는 i 값을 구하는 코드를 작성했으나,
        음수로 부터의 값은 구할 수 없어서 while문을 이용해서 코드를 작성함
      </li>
      <li>num 길이를 가진 배열에 맵돌면서 index + 1 한 값으로 채우기</li>
      <li>채워진 배열의 총합 구해서 sum에 저장하기</li>
      <li>sum이 total 값이랑 같아질때까지 반복문 돌리기</li>
      <li>sum이 total보다 작으면 시작숫자를 1부터 더하기</li>
      <li>sum이 total보다 크면 시작숫자를 1부터 빼면서 계산하기</li>
      <li>
        시작숫자를 구했다면 num 길이만큼 배열을 만들고, 맵돌면서 index값 +
        시작숫자로 채우기
      </li>
      <li>answer 반환</li>
    </ol>
    <ul>
      <li>// for 문</li>
      <li>
        배열의 총합 = (배열 첫번째 숫자 + 배열 마지막 숫자) * 배열의 길이 / 2
      </li>
      <li>1 부터 시작하는 배열의 총합 구하기 ((1 + num) * num) / 2</li>
      <li>total = 초기값 + num * index</li>
      <li>
        시작 숫자 (index)가 구해지면 num 배열만큼 맵돌면서 시작숫자 + ∂로 더해서
        배열 채우기
      </li>
      <li>
        <a href="https://bubblebubble.tistory.com/22" target="_blank"
          >참고 블로그
        </a>
      </li>
    </ul>
  </div>
  <pre>
  <code class="javascript">
  // for문 코드
  function solution(polynomial) {
    var answer = []
    const standard = ((1 + num) * num) / 2
    for(let i = 0 ; i< num; i++){
        if(standard + num * i === total){
            answer = Array(num).fill().map((v, idx)=>{return i+idx + 1})
        } 
    }
     return answer;
  }
  </code>
    <code class="javascript">
  // while문 코드
  function solution(polynomial) {
    var answer = [];
    let firstNum = 1;

    let sum = new Array(num).fill().map((v,idx)=> idx + 1).reduce((acc,cur) => acc+cur)
    while(sum!==total){

    if( sum < total){
      firstNum ++
    }
    else{
      firstNum --
    }

    sum = new Array(num).fill().map((a,i)=>firstNum + i).reduce((acc,cur)=>acc+cur)
    } 
     answer = Array(num).fill().map((a,idx)=> idx + firstNum)
     return answer;
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
