<li><a href="#소인수분해">소인수분해</a></li>

```html

```

```html
<section>
  <a name="소인수분해"> #소인수분해</a>
  <h3>
    Q. 소인수분해란 어떤 수를 소수들의 곱으로 표현하는 것입니다. 예를 들어 12를
    소인수 분해하면 2 * 2 * 3 으로 나타낼 수 있습니다. 따라서 12의 소인수는 2와
    3입니다. 자연수 n이 매개변수로 주어질 때 n의 소인수를 오름차순으로 담은
    배열을 return하도록 solution 함수를 완성해주세요.
  </h3>

  <p>- 2 ≤ n ≤ 10,000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 12 = 결과: [2, 3]</p>
  <p>- n: 17 = 결과: [17]</p>
  <p>- n: 420 = 결과: [2, 3, 5, 7]</p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>
        ※ 소인수 분해 => x를 2부터 x의 제곱근까지의 숫자로 나누어 떨어지는지
        검사하면 됨
      </li>
      <li>2부터 x의 제곱근까지의 숫자까지 반복문 돌리기</li>
      <li>n % i === 0 이 될 때 까지 n을 i로 나누기</li>
      <li>n % i === 0 이 되는 값을 answer에 집어넣기</li>
      <li>
        answer의 length가 1보다 크면 중복제거를 하고, 오름차순 정렬을 한 후 반환
      </li>
      <li>answer의 length가 1이면 answer 반환</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(n) {
  let answer = [];
  for (let i = 2; i <= n; i++) {
    while (n % i === 0) {
      n /= i;
      answer.push(i)
    }
  }
  answer = answer.length > 1 ? [...new Set(answer)].sort((a,b)=>a-b) : answer
  return answer
}
  </code>
</pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>i부터 n까지 반복문 돌리기</li>
    <li>if(num % i == 0)이 되면 num에 num을 i로 나눈 몫을 저장</li>
    <li>answer 배열에 i 집어넣기</li>
    <li>중복제거하고, 정렬 후 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(n) {
    var num = n;
    var A = [];
    for(let i = 2; i < n+1; i++){
        if(num % i == 0){
            num = num / i;
            A.push(i);
            i--;
        }
    }
    var answer = Array.from(new Set(A));

    return answer;
}
  </code>
</pre>
</section>
```
