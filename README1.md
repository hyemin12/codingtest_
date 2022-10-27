<li><a href="#저주의숫자3">저주의숫자3</a></li>

```html

```

```html
<section>
  <a name="저주의숫자3"> #저주의숫자3</a>
  <h3>
    Q. 정수 n이 매개변수로 주어질 때, n을 3x 마을에서 사용하는 숫자로 바꿔
    return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    3x 마을 사람들은 3을 저주의 숫자라고 생각하기 때문에 3의 배수와 숫자 3을
    사용하지 않습니다. 3x 마을 사람들의 숫자는 다음과 같습니다.
  </p>
  <img
    src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F6AKpk%2FbtrPFB30jBb%2FBAtZ4ic80hZPZpy9vOkMf1%2Fimg.jpg"
  />

  <p>- 1 ≤ n ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 15 = 결과: 25</p>
  <p>- n: 40 = 결과: 76</p>

  <hr />
  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>1 ~ n까지 반복하면서 answer + 1 하기</li>
      <li>answer에 3이 들어있거나 3으로 나눈 나머지가 0인 경우에는 1 더하기</li>
      <li>
        ※ 처음에는 while문 돌리지 않고 if문으로 작성했을 때엔 3이 들어가 있는
        경우에는 answer + 1 계산을 하지 못했었음
      </li>
      <li>
        ※ 해당 조건이 false가 될때까지 while문을 돌리도록 설정하니까 코드가
        통과함
      </li>
      <li>
        ※ 해당 조건이 false가 될때까지 while문을 돌리도록 설정하니까 코드가
        통과함
      </li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(n) {
    var answer = 0;  
    for(let i = 1 ; i <= n ; i ++) {
        answer += 1
        while(answer.toString().includes('3') || answer % 3 ===0){
     answer += 1       
        } 
    } 
    return answer;
}
  </code>
</pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>조건1. i가 3으로 나눈 나머지가 0인 경우에는 n(주어진 숫자) + 1하기</li>
    <li>조건2. 3이 포함되어 있고, 나머지가 0이 아닌 경우에도 + 1 하기</li>
  </ul>
  <pre>
  <code class="javascript">
function solution(n) {
    var answer = 0;
    for(let i=1; i<=n; i++){
        if(i%3 == 0){
            n++;
        }
        if(String(i).includes("3")& i%3 != 0){
            n++
        }
    }
    return n;
}
  </code>
</pre>
</section>
```
