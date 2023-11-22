
  ```cpp
  int area = 0, flag = 1; // area 深搜的空间面积 flage = 1 不为与走廊相邻空间
    int largestArea(vector<string>& grid) {
        int res = 0, temp = 0; // res 有效最大值
        for (int i = 0; i < grid.size(); i++) 
            for (int j = 0; j < grid[0].size(); j++) {
                 if (grid[i][j] != '6' && grid[i][j] != '0') {
                     area = 0, flag = 1; // 初始化
                     dfs(grid, grid[i][j], i, j); // 深搜
                     if (flag) res = max(res, area); // 取最大值
                 }
            }
        return res;
    }
    void dfs(vector<string> &grid, char visited, int x, int y) { // 深搜
        grid[x][y] = '6'; //遍历过的点都记作'6'
        area++;
        int dx[4] = {-1, 0, 1, 0}, dy[4] = {0, 1, 0, -1};
        for (int i = 0; i < 4; i++) {
            int a = x + dx[i], b = y + dy[i];
            if (a < 0 || b < 0 || a >= grid.size() || b >= grid[0].size() || grid[a][b] == '0') 
                flag = 0; // 碰倒走廊，flag标记为0,表示该空间面积无效
            if (a >= 0 && b >= 0 && a < grid.size() && b < grid[0].size() && grid[a][b] == visited )
                dfs(grid, grid[a][b], a, b);
        }
    }
  ```

<BarBottom bg-blue-9 text-white title="Algorithm Job 算法设计课程作业">
  <Item text-white text="ileostar/algorithm-job">
    <carbon:logo-github />
  </Item>
  <Item text-white text="algorithm-job.netlify.app">
    <img
      src="https://d33wubrfki0l68.cloudfront.net/273aa82ec83b3e4357492a201fb68048af1c3e6a/8f657/logo.svg"
      class="w-4"
     />
  </Item>
</BarBottom>
