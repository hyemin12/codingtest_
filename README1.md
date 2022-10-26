<li><a href="#합성수찾기">합성수찾기</a></li>

```html

```

```html
<section>
  <a name="합성수찾기"> #합성수찾기</a>
  <h3>
    Q. 약수의 개수가 세 개 이상인 수를 합성수라고 합니다. 자연수 n이 매개변수로
    주어질 때 n이하의 합성수의 개수를 return하도록 solution 함수를 완성해주세요.
  </h3>

  <p>- 1 ≤ n ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 10 = 결과: 5</p>
  <p>- n: 15 = 결과: 8</p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>약수의 판별하는 함수 작성</li>
      <li>해당 숫자의 약수를 저장할 변수 count</li>
      <li>숫자 % i === 0 (약수)라면 count 더하기</li>
      <li>1부터 해당 숫자를 2로 나눈 값까지 반복</li>
      <li>약수가 2 이상이라면 true 반환, 아니라면 false 반환</li>
      <li>합성수 구하는 함수 (solution)</li>
      <li>1부터 n까지 약수 판별하는 함수 반복해서 돌리기</li>
      <li>약수 판별함수가 true 면 answer 더하기 (합성수라면)</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(n) {
    var answer = 0;

    for(let i = 1; i＜=n;i++){
        isMixNum(i) ? answer ++ : null
    }
    return answer;
}

function isMixNum(num){
    let count = 0
    
    for(let i = 1 ; i ＜= (num/2); i ++) {
        num%i === 0 ? count++ : null
    }
    return count >= 2 ? true : false
}
  </code>
</pre>
</section>
```
