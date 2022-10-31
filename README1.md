<li><a href="#안전지대">안전지대</a></li>

```html
<section>
  <a name="안전지대"> #안전지대</a>
  <h3>
    Q. 지뢰가 매설된 지역의 지도 board가 매개변수로 주어질 때, 안전한 지역의 칸
    수를 return하도록 solution 함수를 완성해주세요.
  </h3>
  <br />
  <p>
    다음 그림과 같이 지뢰가 있는 지역과 지뢰에 인접한 위, 아래, 좌, 우 대각선
    칸을 모두 위험지역으로 분류합니다.
  </p>
  <img
    src="https://velog.velcdn.com/images/kwb020312/post/0fc0997d-9a93-47d1-b51d-53bc46214690/image.png"
  />
  <p>
    지뢰는 2차원 배열 board에 1로 표시되어 있고 board에는 지뢰가 매설 된 지역
    1과, 지뢰가 없는 지역 0만 존재합니다.
  </p>
  <br />
  <p>- board는 n * n 배열입니다.</p>
  <p>- 1 ≤ n ≤ 100</p>
  <p>- 지뢰는 1로 표시되어 있습니다.</p>
  <p>- board에는 지뢰가 있는 지역 1과 지뢰가 없는 지역 0만 존재합니다.</p>

  <br />
  <p style="margin-top: 15px">예시)</p>
  <p>
    - board: [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 1, 0,
    0], [0, 0, 0, 0, 0]] = 결과: 16
  </p>
  <p>
    - board: [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 1, 1,
    0], [0, 0, 0, 0, 0]] = 결과: 13
  </p>
  <p>
    - board: [[1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1,
    1, 1, 1, 1], [1, 1, 1, 1, 1, 1], [1, 1, 1, 1, 1, 1]] = 결과: 0
  </p>

  <br />
  <div style="margin-top: 15px; padding: 20px 0; border: 1px solid #ccc">
    <p class="code-title">■ 내가 작성한 코드</p>
    <ol style="margin: 0 0 10px 0">
      <li>폭탄이 있는 위치 찾기</li>
      <li>폭탄이 있는 주변의 값 2로 바꾸기</li>
      <li>칸이 0이면 answer값 더하기</li>
      <li>※ 주변의 값을 2로 바꾸기 코드 작성이 어렵...</li>
    </ol>
  </div>
  <pre>
  <code class="javascript">
function solution(board) {
    var answer = 0;

    for(let i =0; i＜board.length;i++){
        for(let j =0; j＜board[i].length;j++){

        if(board[i][j] ===1){
  
            // 위
            if(i !== 0 && j !== 0 && board[i-1][j-1] !== 1 ) {
                board[i-1][j-1] = 2
            }
            if(i !== 0 && board[i-1][j] !== 1 ) {
                board[i-1][j] = 2   
            }
            if(i !== 0 && j !== board[i].length-1 && board[i-1][j+1] !== 1 ) {
                board[i-1][j+1] = 2
            }

            // 중간
            if(j !== 0 && board[i][j-1] !== 1 && board[i][j-1] !== 1) {
                board[i][j-1] = 2
            }
            if(j !== board[i].length-1 && board[i][j+1] !== 1) {
                board[i][j+1] = 2
            }

            // 아래
            if(i !== board.length-1 && j !== 0 && board[i+1][j-1] !== 1 ) {
                board[i+1][j-1] = 2
            }
            if(i !== board.length-1 && board[i+1][j] !== 1 && board[i+1][j] !== 1) {
                board[i+1][j] = 2
            }
            if(i !== board.length-1 && j !== board[i].length-1 && board[i+1][j+1] !== 1) {
                board[i+1][j+1] = 2
          }     
        }
      }
    }            
    board.map((v)=> v.map((a)=>a === 0 ? answer++ : ''))

    return answer;
}
  </code>
</pre>
</section>
```
