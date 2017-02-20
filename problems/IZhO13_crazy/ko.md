이 문제는 확률론에서 매우 잘 알려진 퍼즐을 적절히 바꾼 것입니다. 비행기에 $N$개의 좌석이 있고 각 좌석은 승객들에게 배정되어 있습니다. 승객들은 한 명씩 좌석 번호 순서대로 1번부터 $N$번까지 차례대로 들어옵니다. ($1$번 좌석이 배정된 승객이 가장 먼저 들어오고, $2$번 좌석이 배정된 승객이 두 번째로 들어오고, ...)

이렇게 하면 줄이 너무 길어져 성질 급한 지학이가 버틸 수가 없기 때문에, 지학이는 맨 앞으로 가서 맨 처음 들어갑니다. (1번 좌석에 배정받지 않더라도) 또한 그는 그가 원하는 좌석에 앉습니다. (자신이 배정받은 좌석에 앉을 수도 있겠죠)

지학이가 앉은 뒤, 다음 승객들은 배정받은 좌석 번호 순서대로 입장하여 아래 방식대로 앉을 자리를 정합니다.

* 배정받은 좌석이 비어 있다면 그 자리에 앉습니다.
* 배정받은 좌석이 비어 있지 않다면 남은 좌석 중 아무 자리에나 앉습니다.

그럼 마지막으로 들어온 승객은 어느 자리에 앉게 될까요? 답은 간단합니다: 이 승객은 원래 배정받은 자리에 앉거나 지학이가 배정받은 자리에 앉게 됩니다!

지학이가 $j$번 좌석에 앉았다고 가정합시다. 지학이가 배정받은 좌석은 $j$번 좌석이 아닙니다. $j$번 좌석에 배정받은 승객이 비행기 안에 들어오면, 그는 남은 좌석 중에 아무 좌석이나 앉게 됩니다. 이 상황은 다음에 입장할 승객들에게도 똑같이 반복됩니다. 하지만 이 승객이 지학이가 배정받은 좌석에 앉는다면, 당연히 (!) 그 승객 다음에 입장하는 승객들은 원래 자리에 앉게 되겠죠. 이 문제에서 우리는 지학이가 배정받은 좌석 번호를 알고자 합니다.

### 입력 형식

입력 파일은 여러 개의 테스트 케이스로 구성됩니다. 첫 번째 줄에는 테스트 케이스의 수 $T$가 주어집니다. ($1 \le T \le 10$). 다음 $T$개 줄에는 $N+1$개의 정수가 공백을 사이로 두고 주어집니다. 첫 번째 정수는 승객의 수 $N$ ($1 \le N \le 10^{3}$)입니다. 이후 입장한 순서대로 각 승객이 앉은 좌석 번호 $p_{1}, p_{2}, \cdots, p_{N}$ 이 주어집니다. 즉 $i$번째로 입장한 승객은 $p_{i}$번 좌석에 앉았습니다. 모든 입력은 위에서 주어진 조건을 만족합니다.

### 출력 형식

각 테스트 케이스마다 지학이가 배정받은 좌석이 유일하게 결정된다면 좌석 번호를 출력하고, 그렇지 않다면 0을 출력하세요.

### 예제

<table class='table table-bordered table-condensed'>
 <thead>
  <tr>
   <th style="width: 50%;">입력</th>
   <th style="width: 50%;">출력</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td class="code-font">2<br/>
2 2 1<br/>
4 2 3 1 4</td>
   <td class="code-font">0<br/>
1</td>
  </tr>
 </tbody>
</table>

### 참고

편의상 $i$번 승객을 $i$번 좌석을 배정받은 승객으로 둡시다. 즉 $i$번 승객과 $i$번째로 입장한 승객이 다를 수도 있습니다.

`2 2 1`에서 답을 정확히 결정할 수 없습니다.

* 지학이가 1번 승객: 지학이가 첫 번째로 입장해서 2번 좌석을 선택합니다. 2번 승객은 울며 겨자먹기로 1번 좌석에 앉게 됩니다.
* 지학이가 2번 승객: 지학이가 첫 번째로 입장해서 2번 좌석을 선택합니다. 1번 승객은 1번 좌석이 비었으므로 1번 좌석에 앉습니다.

`2 3 1 4`에서 답을 정확히 결정할 수 있습니다.

* 지학이가 1번 승객: 지학이가 첫 번째로 입장해서 2번 좌석을 선택합니다. 2번 승객은 두 번째로 입장해서 3번 좌석을, 3번 승객은 세 번째로 입장해서 1번 좌석을 선택했네요. 4번 승객은 자동으로 4번 좌석에 앉게 되겠습니다.
* 지학이가 2 ~ 4번 승객: 지학이가 첫 번째로 입장해서 2번 좌석을 선택합니다. 1번 승객은 두 번째로 입장해서 1번 좌석에 앉았네요. 따라서 입력과 다르므로 유효하지 않습니다.