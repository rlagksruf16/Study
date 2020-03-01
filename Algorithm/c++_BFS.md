## C++ BFS 정리 [C++]



- BFS는 너비 우선 탐색이라는 뜻으로 그래프 탐색 전략 중 하나이다.

- BFS는 stl의 큐를 활용하여 구현한다.


  

  ------

  

  #### BFS 팀섹

  > BFS 또한 DFS 와 마찬가지로 시작 정점부터 시작하여 인접한 정점을 반복하는 식으로 진행된다.
  >
  > 하지만 DFS가 깊이 우선 탐색(수직 개념으로 이해하는 게 편함) 이라면 BFS는 너비 우선 탐색(수평 개념)으로 동일 선상에 있는 정점들 부터 방문한다.
  >

 #### 인접리스트로 구현한 BFS

```c++

const int Max = 1001;

vector<int> adj[Max];
bool visit[Max];
queue<int> q;

void bfs(int start) {
    visit[start] = true;
    q.push(start);

    while(!q.empty()) {
        int x = q.front();
        q.pop();

        for(int i = 0; i < adj[start].size(); i++) {
            int next = adj[start][i];
            if(!visit[next]) {
                visit[next] = true;
                q.push(next);
            }
        }
    }
}

```