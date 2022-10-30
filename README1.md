<li><a href="#유한소수판별하기">유한소수판별하기</a></li>

```html

```

```html
<section>
  <a name="유한소수판별하기"> #유한소수판별하기</a>
  <h3>
    Q. 두 정수 a와 b가 매개변수로 주어질 때, a/b가 유한소수이면 1을,
    무한소수라면 2를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <br />
  <p>
    소수점 아래 숫자가 계속되지 않고 유한개인 소수를 유한소수라고 합니다. 분수를
    소수로 고칠 때 유한소수로 나타낼 수 있는 분수인지 판별하려고 합니다.
    유한소수가 되기 위한 분수의 조건은 다음과 같습니다.
  </p>
  <p>- 기약분수로 나타내었을 때, 분모의 소인수가 2와 5만 존재해야 합니다.</p>

  <p>- a, b는 정수</p>
  <p>- 0 < a ≤ 1,000</p>
  <p>- 0 < b ≤ 1,000</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- a: 7 b: 20 = 결과: 1</p>
  <p>- a: 11 b: 22 = 결과: 1</p>
  <p>- a: 12 b: 21 = 결과: 2</p>

  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>divisor 최대 공약수 구하기</li>
      <li>divisor(최대공약수)가 없으면 b를 소인수분해하기</li>
      <li>최대 공약수가 있으면 b / divisor값을 소인수분해하기</li>
      <li>소인수분해 함수만들기</li>
      <li>facArr = 소인수분해에서 반환된 배열</li>
      <li>2와 5가 아닌 수만 필터링하기</li>
      <li>facArr 길이가 0이면 1 반환, 아니면 2 반환</li>
      <li>
        ※ 코드가 길고 복잡함.. 나중에 보면 어떤 함수인지 알아보기 힘들 것
        같음...
      </li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(a, b) {
    var answer = 0;
    let divisor = 0;
    
    for(let i =2; i＜Math.max(a,b);i++){
        if( a % i ===0 && b % i ===0){
            divisor = i
        } 
    }
    let facArr = divisor === 0 ? factorization(b) : factorization(b / divisor)
    
    facArr = [...facArr].filter((v)=> v !== 2 && v !== 5 ); 
    
    answer = facArr.length === 0 ? 1 : 2
    return answer;
}

function factorization(num){
    let arr = []
    for(let j = 2; j<= num;j++){
        while(num % j === 0){
            num /= j
            arr.push(j)
        }
    }
    return arr;
}
  </code>
</pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>n = 최대 공약수</li>
    <li>b를 최대 공약수로 나누기</li>
    <li>b%2===0 이면 b/=2</li>
    <li>b%5===0 이면 b/=5</li>
    <li>b가 1이면 1 반환 아니면 2 반환</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(a, b) {
    let n = 1;
    for (let i = 1; i <= Math.min(a,b); i++) {
        if (a%i===0 && b%i===0) n = i;
    }

    b/=n;
    
    while (b%2===0) b/=2;
    while (b%5===0) b/=5;

    return b === 1 ? 1 : 2; 
}
  </code>
</pre>
</section>
```
