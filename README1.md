<li><a href="#문자반복출력하기">문자반복출력하기</a></li>
<li><a href="#양꼬치">양꼬치</a></li>

```html
<section>
  <a name="아이스아메리카노"> #아이스아메리카노</a>
  <h3>
    Q. 머쓱이는 추운 날에도 아이스 아메리카노만 마십니다. 아이스 아메리카노는
    한잔에 5,500원입니다. 머쓱이가 가지고 있는 돈 money가 매개변수로 주어질 때,
    머쓱이가 최대로 마실 수 있는 아메리카노의 잔 수와 남는 돈을 순서대로 담은
    배열을 return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>
    - 1 ≤ num_list의 길이 ≤ 1,000
    <br />
    - 0 ≤ num_list의 원소 ≤ 1,000
    <br />
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- num_list: [1, 2, 3, 4, 5] = 결과: [5, 4, 3, 2, 1]</p>
  <p>- num_list: [1, 1, 1, 1, 1, 2] = 결과: [2, 1, 1, 1, 1, 1]</p>
  <p>- num_list: [1, 0, 1, 1, 1, 3, 5] = 결과: [5, 3, 1, 1, 1, 0, 1]</p>

  <pre>
    <code class="javascript">   
function solution(money) {
  var answer = [];
  
  answer.push(parseInt(money / 5500), money % 5500)
  
  return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="문자반복출력하기"> #문자반복출력하기</a>
  <h3>
    Q. 문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string에 들어있는 각
    문자를 n만큼 반복한 문자열을 return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>
    - 1 ≤ my_string 길이 ≤ 50
    <br />
    - 1 ≤ n ≤ 50
    <br />
    - "my_string"은 영어 대소문자로 이루어져 있습니다.
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- my_string: "hello" n: 3 = 결과: "hhheeellllllooo"</p>

  <pre>
    <code class="javascript">   
function solution(my_string, n) {
  var answer = '';
  
  for(let i =0;i＜my_string.length;i++){
      answer += my_string[i].repeat(n)
  }
  return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="양꼬치"> #양꼬치</a>
  <h3>
    Q. 머쓱이네 양꼬치 가게는 10인분을 먹으면 음료수 하나를 서비스로 줍니다.
    양꼬치는 1인분에 12,000원, 음료수는 2,000원입니다. 정수 n과 k가 매개변수로
    주어졌을 때, 양꼬치 n인분과 음료수 k개를 먹었다면 총얼마를 지불해야 하는지
    return 하도록 solution 함수를 완성해보세요.
  </h3>
  <p>
    - 0 < n < 1,000
    <br />
    - n / 10 ≤ k < 1,000
    <br />
    - 서비스로 받은 음료수는 모두 마십니다.
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 10 k: 3 = 결과: 124,000</p>
  <p>- n: 64 k: 6 = 결과: 768,000</p>

  <pre>
    <code class="javascript">   
function solution(n, k) {
  var answer = 0;
  let service = n>= 10 ? parseInt(n /10) : 0
  
  answer = 12000 * n + 2000 * k - 2000 * service
  
  return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <pre>
  <code class="javascript">   
function solution(n, k) {
  return n*12000 + k*2000 - parseInt(n/10)*2000
}
  </code>
</pre>
</section>
<section>
  <a name="n의배수고르기"> #n의배수고르기</a>
  <h3>
    Q. 정수 n과 정수 배열 numlist가 매개변수로 주어질 때, numlist에서 n의 배수가
    아닌 수들을 제거한 배열을 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    - 1 ≤ n ≤ 10,000
    <br />
    - 1 ≤ numlist의 크기 ≤ 100
    <br />
    - 1 ≤ numlist의 원소 ≤ 100,000
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 3 numlist: [4, 5, 6, 7, 8, 9, 10, 11, 12] = 결과: [6, 9, 12]</p>
  <p>- n: 5 numlist: [1, 9, 3, 10, 13, 5] = 결과: [10, 5]</p>
  <p>- n: 12 numlist: [2, 100, 120, 600, 12, 12] = 결과: [120, 600, 12, 12]</p>

  <pre>
    <code class="javascript">   
function solution(n, numlist) {
    var answer = numlist.filter((v)=> v % n === 0);
    return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="머쓱이보다키큰사람"> #머쓱이보다키큰사람</a>
  <h3>
    Q. 머쓱이는 학교에서 키 순으로 줄을 설 때 몇 번째로 서야 하는지
    궁금해졌습니다. 머쓱이네 반 친구들의 키가 담긴 정수 배열 array와 머쓱이의 키
    height가 매개변수로 주어질 때, 머쓱이보다 키 큰 사람 수를 return 하도록
    solution 함수를 완성해보세요.
  </h3>
  <p>
    - 1 ≤ array의 길이 ≤ 100
    <br />
    - 1 ≤ height ≤ 200
    <br />
    - 1 ≤ array의 원소 ≤ 200
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- arr: [149, 180, 192, 170] height: 167 = 결과: 3</p>
  <p>- arr: [180, 120, 140] height: 190 = 결과: 0</p>

  <pre>
    <code class="javascript">   
function solution(array, height) {
  var answer = 0;
  answer = array.filter((v)=> v > height).length
  
  return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="피자나눠먹기"> #피자나눠먹기</a>
  <h3>
    Q. 머쓱이네 피자가게는 피자를 일곱 조각으로 잘라 줍니다. 피자를 나눠먹을
    사람의 수 n이 주어질 때, 모든 사람이 피자를 한 조각 이상 먹기 위해 필요한
    피자의 수를 return 하는 solution 함수를 완성해보세요.
  </h3>
  <p>- 1 ≤ n ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- n: 7 = 결과: 1</p>
  <p>- n: 1 = 결과: 1</p>
  <p>- n: 15 = 결과: 3</p>

  <pre>
    <code class="javascript">   
function solution(n) {
  var answer = Math.ceil(n/7)
  return answer;
}
    </code>
  </pre>
</section>
<section>
  <a name="배열원소길이"> #배열원소길이</a>
  <h3>
    Q. 문자열 배열 strlist가 매개변수로 주어집니다. strlist 각 원소의 길이를
    담은 배열을 retrun하도록 solution 함수를 완성해주세요.
  </h3>
  <p>
    - 1 ≤ strlist 원소의 길이 ≤ 100<br />
    - strlist는 알파벳 소문자, 대문자, 특수문자로 구성되어 있습니다.
  </p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- strlist: ["We", "are", "the", "world!"] = 결과: [2, 3, 3, 6]</p>
  <p>- strlist: ["I", "Love", "Programmers."] = 결과: [1, 4, 12]</p>

  <pre>
    <code class="javascript">   
function solution(strlist) {
  var answer = [];
  for(let i =0; i＜strlist.length;i++){
      answer.push(strlist[i].length)
  }
  return answer;
}
    </code>
  </pre>
  <p class="code-title">■ 다른 사람 작성 코드</p>
  <pre>
  <code class="javascript">   
function solution(strlist) {
  return strlist.map((el) => el.length)
}
  </code>
</pre>
</section>
<section>
  <a name="문자열안에문자열"> #문자열안에문자열</a>
  <h3>
    Q. 문자열 str1, str2가 매개변수로 주어집니다. str1 안에 str2가 있다면 1을
    없다면 2를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <p>- 1 ≤ str1의 길이 ≤ 100 <br />- 1 ≤ str2의 길이 ≤ 100</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>- str1: "ab6CDE443fgh22iJKlmn1o" str2: "6CD" = 결과: 1</p>
  <p>- str1: "ppprrrogrammers" str2: "pppp" = 결과:2</p>

  <pre>
    <code class="javascript">   
function solution(str1, str2) {
    var answer = 0;
    answer = str1.includes(str2) ? 1 : 2
    return answer;
}
    </code>
  </pre>
</section>
```
