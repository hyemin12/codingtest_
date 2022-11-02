<li><a href="#신고결과받기">신고결과받기</a></li>

```html
<section>
  <a name="신고결과받기"> #신고결과받기</a>
  <h3>
    Q. 이용자의 ID가 담긴 문자열 배열 id_list, 각 이용자가 신고한 이용자의 ID
    정보가 담긴 문자열 배열 report, 정지 기준이 되는 신고 횟수 k가 매개변수로
    주어질 때, 각 유저별로 처리 결과 메일을 받은 횟수를 배열에 담아 return
    하도록 solution 함수를 완성해주세요.
  </h3>
  <br />

  <p>- 1 ≤ babbling의 길이 ≤ 100</p>
  <p>- 1 ≤ babbling[i]의 길이 ≤ 15</p>
  <p>
    - babbling의 원소에서 "aya", "ye", "woo", "ma"는 각각 최대 한 번씩만
    등장합니다.
  </p>
  <p>- 문자열은 알파벳 소문자로만 이루어져 있습니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- babbling: ["aya", "yee", "u", "maa", "wyeoo"] = 결과: 1</p>
  <p>- babbling: ["ayaye", "uuuma", "ye", "yemawoo", "ayaa"] = 결과:3</p>

  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>babbling을 맵 돌면서 발음할 수 있는 발음을 기준으로 나누기</li>
      <li>발음할 수 있다면 '' 이 반환됨</li>
      <li>''을 가진 값만 필터링 하고, 길이 반환하기</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(babbling) {
    var answer = 0;
    
   const split = babbling.map((word) => 
        word.split(/aya|ye|woo|ma/).join('')    
    )
   answer = split.filter((v)=> v === '').length
    
    return answer;
}
  </code>
</pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <ul style="margin: 0 0 10px 0">
    <li>
      map 사용안하고 forEach + 조건문을 사용하면 보다 깔끔한 코드 작성 가능
    </li>
  </ul>
  <pre>
  <code class="javascript">
function solution(babbling) {
    let counter = 0;
    babbling.forEach(element => {
        if (element.split(/aya|ye|woo|ma/g).join('') === '') {
            counter++;
        }
    });
    return counter;
}
  </code>
</pre>
</section>
```
