<li><a href="#특이한정렬">특이한정렬</a></li>

```html
<section>
  <a name="삼각형의완성조건2"> #삼각형의완성조건2</a>
  <h3>
    Q. 삼각형의 두 변의 길이가 담긴 배열 sides이 매개변수로 주어집니다. 나머지
    한 변이 될 수 있는 정수의 개수를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    선분 세 개로 삼각형을 만들기 위해서는 다음과 같은 조건을 만족해야 합니다.
  </p>
  <p>가장 긴 변의 길이는 다른 두 변의 길이의 합보다 작아야 합니다.</p>
  <br />
  <p>- sides의 원소는 자연수입니다.</p>
  <p>- sides의 길이는 2입니다.</p>
  <p>- 1 ≤ sides의 원소 ≤ 1,000</p>
  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- sides: [1, 2] = 결과: 1</p>
  <p>- sides: [3, 6] = 결과: 5</p>
  <p>- sides: [11, 7] = 결과: 13</p>
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>1. 가장 긴변이 b인 경우</li>
      <li>b < a + c</li>
      <li>max = min + c</li>
      <li>c = max + min</li>
      <li>c ~ max</li>
      <li>c - max</li>
      <li>2. 나머지 한변이 제일 긴 경우</li>
      <li>a + b > c > max(a,b)</li>
      <li>min + max > c > max</li>
      <li>c = min + max - 1 - max</li>
      <li>c = min - 1</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(sides) {
    var answer = 0;
    const min = Math.min(...sides)
    const max = Math.max(...sides)
    const c = max + min
    answer = min * 2 -1

    return answer;
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
