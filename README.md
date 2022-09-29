<section>
        <h4>
          Q. 행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의
          값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬
          덧셈의 결과를 반환하는 함수, solution을 완성해주세요.
        </h4>
        <p>행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.</p>
        <p style="margin-top: 15px">예시)</p>
        <p>
          - arr1 = [[1,2],[2,3]] / arr2= [[3,4],[5,6]] / 결과: [[4,6],[7,9]]
        </p>
        <p>- arr1 = [[1],[2]] / arr2= [[3],[4]] / 결과: [[4],[6]]</p>

        코드팬주소
        <h4>타이틀</h4>
        <p>
          arr1 = [[1,2],[2,3]]<br />
          arr2 = [[3,4],[5,6]]<br />
          result = [[4,6],[7,9]]<br />
          <br />
          arr1[0][0] + arr2[0][0] = result[0][0]
          <span style="color: green; margin-left: 10px">// 1 + 3 = 4</span
          ><br />
          arr1[0][1] + arr2[0][1] = result[0][1]<span
            style="color: green; margin-left: 10px"
          >
            // 2 + 4 = 6</span
          >
          <br />

          <br />
          ...반복
        </p>
      </section>

---

---

참고

- https://hw1205.tistory.com/45
- enai.tistory.com
