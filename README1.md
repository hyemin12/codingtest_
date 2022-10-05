<li><a href="#점의위치구하기">점의위치구하기</a></li>
<li><a href="#문자반복출력하기">문자반복출력하기</a></li>
<li><a href="#양꼬치">양꼬치</a></li>

```html
<section>
  <a name="배열의유사도"> #배열의유사도</a>
  <h3>
    Q. 두 배열이 얼마나 유사한지 확인해보려고 합니다. 문자열 배열 s1과 s2가
    주어질 때 같은 원소의 개수를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    - 1 ≤ s1, s2의 길이 ≤ 100<br />
    - 1 ≤ s1, s2의 원소의 길이 ≤ 10<br />
    - s1과 s2의 원소는 알파벳 소문자로만 이루어져 있습니다<br />
    - s1과 s2는 각각 중복된 원소를 갖지 않습니다.
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- s1:["a", "b", "c"] s2: ["com", "b", "d", "p", "c"] = 결과: 2</p>
  <p>- s1: ["n", "omg"] s2: ["m", "dot"] = 결과: 0</p>

  <pre>
    <code class="javascript">   
function solution(s1, s2) {
  var answer = 0;
  for(let i = 0; i＜s1.length;i++){
    const count = s2.filter((v)=>v === s1[i]).length 
      answer += count
  }
  return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <p></p>
  <pre>
  <code class="javascript">   
function solution(s1, s2) {
  const intersection = s1.filter((x) => s2.includes(x));
  return intersection.length;
}
  </code>
</pre>
</section>
```
