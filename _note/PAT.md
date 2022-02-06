# PAT甲级

## 1076 Forwards on Weibo (30 分)
Weibo is known as the Chinese version of Twitter. One user on Weibo may have many followers, and may follow many other users as well. Hence a social network is formed with followers relations. When a user makes a post on Weibo, all his/her followers can view and forward his/her post, which can then be forwarded again by their followers. Now given a social network, you are supposed to calculate the maximum potential amount of forwards for any specific user, assuming that only L levels of indirect followers are counted.

**Input Specification:**
Each input file contains one test case. For each case, the first line contains 2 positive integers: N (≤1000), the number of users; and L (≤6), the number of levels of indirect followers that are counted. Hence it is assumed that all the users are numbered from 1 to N. Then N lines follow, each in the format:
```
M[i] user_list[i]
```
where M[i] (≤100) is the total number of people that user[i] follows; and user_list[i] is a list of the M[i] users that followed by user[i]. It is guaranteed that no one can follow oneself. All the numbers are separated by a space.

Then finally a positive K is given, followed by K UserID's for query.

**Output Specification:**
For each UserID, you are supposed to print in one line the maximum potential amount of forwards this user can trigger, assuming that everyone who can view the initial post will forward it once, and that only L levels of indirect followers are counted.

**Sample Input:**
```
7 3 共有7个用户 转发层数上限为3
3 2 3 4 一号用户关注了二三四号用户
0 二号用户没有关注
2 5 6 三号用户关注了五六号用户
2 3 1 四号用户关注了三一号用户
2 3 4 ...
1 4
1 5
2 2 6
```

**Sample Output:**
```
4
5
```
**Reference:**

```cpp
// BFS搜索有向图
#include<cstdio>
#include<cstring>
#include<vector>
#include<queue>

using namespace std;
const int MAXV = 1010;
struct Node {
    int id;
    int layer;
};
vector<Node> Adj[MAXV];
bool inq[MAXV] = {false};

int BFS(int s, int L) {// s为起始结点 L为层数上限
    int numForward = 0; // 转发数
    queue<Node> q;
    Node start;
    start.id = s;
    start.layer = 0;
    q.push(start);
    inq[start.id] = true;
    while (!q.empty()) {
        Node topNode = q.front();
        q.pop();
        int u = topNode.id;
        for (int i = 0; i < Adj[u].size(); i++) {
            Node next = Adj[u][i];
            next.layer = topNode.layer + 1;
            if (!inq[next.id] && next.layer <= L) {
                q.push(next);
                inq[next.id] = true;
                numForward++;
            }
        }
    }
    return numForward;
}

int main() {
    Node user;
    int n, L, numFollow, idFollow;
    scanf("%d%d", &n, &L);
    for (int i = 1; i <= n; i++) {
        user.id = i;
        scanf("%d", &numFollow); // i号用户关注的人数
        for (int j = 0; j < numFollow; j++) {
            scanf("%d", &idFollow); // i号用户关注的用户的编号
            Adj[idFollow].push_back(user); // 边idFollow -> i
        }
    }
    int nunQuery, s;
    scanf("%d", &nunQuery); // 查询个数
    for (int i = 0; i < nunQuery; i++) {
        memset(inq, false, sizeof(inq)); // inq数组初始化
        scanf("%d", &s); // 起始结点编号
        int numForward = BFS(s, L); // 返回转发数
        printf("%d\n", numForward);
    }
    return 0;
}
```