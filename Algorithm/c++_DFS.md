## C++ DFS 정리 [C++]



- DFS는 깊이 우선 탐색이라는 뜻으로 그래프 탐색 전략 중 하나이다.

- DFS를 C++ 로 구현하는 방법은 인접행렬과 인접리스트 총 2가지 이다.


  

  ------

  

  #### DFS 팀섹

  > DFS는 시작 정점부터 출발하여 현재 방문하고 있는 정점과 인접한 정점을 하나씩 검사하면서 방문하지 않은 정점을 방문하는 식으로 깊이 방문한다.
  >
  > 만약 더이상 방문할 정점이 존재하지 않는다면 마지막에 따라왔던 간선을 따라 뒤로 돌아가면서 인접한 정점을 방문하는 탐색을 반복한다.
  >

 #### 인접리스트로 구현한 DFS

```c++

const int Max = 1001;

vector<int> adj[Max];
bool visit[Max];

void dfs(int start) {
    visit[start] = true;

    for(int i = 0; i < adj[start].size(); i++) {
        int next = adj[start][i];

        if(visit[next] == false) {
            dfs(next);
        }
    }
}


```