# Assignment #4: Leaderboard

## Problem

You're developing a gaming leaderboard for an online multiplayer game. Players report their scores in real-time. You need to maintain a dynamic data structure that can efficiently add a player's score, get the rank of a player, and get the `k`-th ranked score.

Implement the following methods for the `Leaderboard` class:

- `add_score(player_id: int, score: int) -> int`: Adds a player's score to the leaderboard. If the player already exists, their score is updated. The method should return the player's rank after adding the score. The rank is defined as the number of players with higher scores plus one. If two players have the same score, they share the same rank.

- `get_rank(player_id: int) -> int`: Returns the rank of the player with the given `player_id`. If the player does not exist, return `-1`.

- `get_score_by_rank(rank: int) -> int`: Returns the score of the player with the given rank. If the rank is invalid (greater than the number of players), return `-1`.

온라인 멀티플레이어 게임을 위한 게임 리더보드를 개발하고 있습니다. 플레이어의 점수를 추가하고, 순위를 조회하고, `k`번째 순위의 점수를 가져오는 작업을 효율적으로 처리할 수 있는 시스템을 구현하세요.

`Leaderboard` 클래스에 다음 메서드들을 구현하세요:

- `add_score(player_id: int, score: int) -> int`: 플레이어의 점수를 리더보드에 추가합니다. 이미 존재하는 플레이어일 경우, 점수를 업데이트합니다. 이 메서드는 점수를 추가한 후 해당 플레이어의 순위를 반환해야 합니다. 순위는 더 높은 점수를 가진 플레이어의 수에 1을 더한 값으로 정의됩니다. 두 플레이어가 같은 점수를 가질 경우, 같은 순위를 공유합니다.

- `get_rank(player_id: int) -> int`: 주어진 `player_id`를 가진 플레이어의 순위를 반환합니다. 플레이어가 존재하지 않으면 `-1`을 반환합니다.

- `get_score_by_rank(rank: int) -> int`: 주어진 순위의 플레이어 점수를 반환합니다. 순위가 유효하지 않으면(플레이어 수보다 큰 경우) `-1`을 반환합니다.

## Input specification

The names of the functions and their respective parameters will be provided in the order they are called.

Functions will be separated by a newline, and the parameters of the functions will be separated by whitespace.

함수의 이름과 해당 매개변수들이 호출된 순서대로 제공됩니다.

각 함수 호출은 개행(newline)으로 구분되며, 함수의 매개변수들은 공백으로 구분됩니다.

## Output specification

For each call to `add_score(player_id, score)`, output the **rank** of the player after the score is added or updated, followed by a single newline.

For each call to `get_rank(player_id)`, output the **current rank** of the player with the given `player_id`, or `-1` if the player does not exist, followed by a single newline.

For each call to `get_score_by_rank(rank)`, output the **score** of the player with the given rank, or `-1` if the rank is invalid, followed by a single newline.

`add_score(player_id, score)`가 호출될 때마다, 점수가 추가되거나 갱신된 후 해당 플레이어의 순위를 출력하고, 개행(newline)을 추가합니다.  

`get_rank(player_id)`가 호출될 때마다, 주어진 `player_id`를 가진 플레이어의 현재 순위를 출력하고, 플레이어가 존재하지 않을 경우 `-1`을 출력한 뒤 개행(newline)을 추가합니다.  

`get_score_by_rank(rank)`가 호출될 때마다, 주어진 순위에 해당하는 플레이어의 점수를 출력하고, 순위가 유효하지 않을 경우 -1을 출력한 뒤 개행(newline)을 추가합니다.  

### Sample 0

```plaintext
<< in
add_score 1 100
get_rank 1
add_score 1 120
get_rank 1
add_score 2 100
get_rank 1
get_rank 2
get_score_by_rank 1

>> out
1
1
1
1
2
1
2
120
```

### Sample 1

```plaintext
<< in
add_score 1 100
add_score 2 200
add_score 3 150
add_score 1 250
get_rank 1
get_rank 2
get_rank 3
get_score_by_rank 1
get_score_by_rank 2
get_score_by_rank 3
get_score_by_rank 4
get_score_by_rank 0

>> out
1
1
2
1
1
2
3
250
200
150
-1
-1
```

### Sample 2

```plaintext
<< in
add_score 1 100
get_rank 1
add_score 2 100
get_rank 1
get_rank 2
add_score 1 90
add_score 3 90
get_score_by_rank 3

>> out
1
1
1
1
1
1
3
90
```

### Sample 3

```plaintext
<< in
add_score 1 300
add_score 2 200
add_score 3 200
add_score 4 150
get_rank 1
get_rank 2
get_rank 3
get_rank 4
get_score_by_rank 2
get_score_by_rank 3
get_score_by_rank 4
>> out
1
2
2
4
1
2
2
4
200
200
150
```
