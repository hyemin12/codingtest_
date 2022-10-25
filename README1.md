<li><a href="#구슬을나누는경우">구슬을나누는경우</a></li>

```html

```

```html
<section>
  <a name="구슬을나누는경우"> #구슬을나누는경우</a>
  <h3>
    Q. 머쓱이는 구슬을 친구들에게 나누어주려고 합니다. 구슬은 모두 다르게
    생겼습니다. 머쓱이가 갖고 있는 구슬의 개수 balls와 친구들에게 나누어 줄 구슬
    개수 share이 매개변수로 주어질 때, balls개의 구슬 중 share개의 구슬을 고르는
    가능한 모든 경우의 수를 return 하는 solution 함수를 완성해주세요.
  </h3>

  <p>- 1 ≤ balls ≤ 30</p>
  <p>- 1 ≤ share ≤ 30 0</p>
  <p>- 구슬을 고르는 순서는 고려하지 않습니다.</p>
  <p>- share ≤ balls</p>
  <br />
  <p>힌트</p>
  <img src="" alt="n! / (n-m)! * m!" />

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- balls: 3 share: 2] = 결과: 3</p>
  <p>- balls: 5 share: 3 = 결과: 10</p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>balls * balls - 1 * balls -2 ...</li>
      <li>반복하는 팩토리얼 함수 만들기</li>
      <li>
        힌트를 참고해서 최종값 구하기<br />
        factorial(balls) / (factorial((balls-share)) * factorial(share))
      </li>
      <li>
        ※ 8개가 오류가 계속 나서 다른사람들의 풀이를 찾아보니, BigInt()를 형식을
        사용해야 balls 와 share의 범위를 감당할 수 있다는 것을 알게됨
      </li>
      <li>※ BigInt() : 길이의 제약 없이 정수를 다룰 수 있게 해주는 숫자형</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(balls, share) {
    return factorial(balls) / (factorial((balls-share)) * factorial(share))
}
    
function factorial(num) {
    let result = 1
    for(let i = num; i >= 2; i-- ) {
        result*= i
    }
    return result
}
  </code>
</pre>

  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>※ BigInt()</li>
    <li>※ Math.round()를 사용해 정수로 만들기</li>
  </ul>
  <pre>
  <code class="javascript">
// BigInt()
function solution(balls, share) {
  const [n, m] = [balls, share];
  const fact = [BigInt(1), BigInt(1)];

  for (let i = 2; i <= n; i++) fact[i] = fact[i - 1] * BigInt(i);

  return Number(fact[n] / (fact[n - m] * fact[m]));
}

// Math.round()
function solution(balls, share) {
    function fac(n){
        var i = 1;
        for(var j = 2; j <= n; j++) i*= j;
        return i;
    }
    var answer = Math.round(fac(balls) / (fac(balls-share) * fac(share)));

    return answer;
}
  </code>
</pre>
</section>
```
