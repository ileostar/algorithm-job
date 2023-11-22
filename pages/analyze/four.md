## 1-3 求解

引进一个二维数组c[][]，用c[i][j]记录X[i]与Y[j] 的LCS 的长度，b[i][j]记录c[i][j]是通过哪一个子问题的值求得的，以决定搜索的方向。
我们是自底向上进行递推计算，那么在计算c[i,j]之前，c[i-1][j-1]，c[i-1][j]与c[i][j-1]均已计算出来。此时我们根据X[i] = Y[j]还是X[i] != Y[j]，就可以计算出c[i][j]。
<ul flex w-full>
  <li list-none>
  问题的递归式写成：

  <img src="https://img.leostar.top/study/lcs_1.PNG" rd-2 my-5 mb-10 />
  回溯输出最长公共子序列过程：（我觉得箭头反过来看要好理解些）
  </li>
  <li flex-1 list-none>

  <img src="https://img.leostar.top/study/lcs_2.PNG" rd-2 style="" />
  </li>
</ul>

<arrow v-click="[1, 2]" x1="550" y1="150" x2="740" y2="300" color="#564" width="3" arrowSize="1" />

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
