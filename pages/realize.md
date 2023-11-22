# 02-算法实现

```ts {all|1-2|4-5|6|7|8-17|all}
char a[MAXSTRLEN], b[MAXSTRLEN];
int dp[MAXSTRLEN][MAXSTRLEN], path[MAXSTRLEN][MAXSTRLEN];

///求序列x和y的LCS，path保存路径指向，以方便打印公共子序列
int Lcs(char x[], char y[]){
	int i, j, len1 = strlen(x + 1), len2 = strlen(y + 1);
	memset(dp, 0, sizeof(dp));
	for (i = 1; i <= len1; ++i){
    for (j = 1; j <= len2; ++j){
			if (x[i] == y[j])
				dp[i][j] = dp[i - 1][j - 1] + 1, path[i][j] = 1;
			else if (dp[i - 1][j] >= dp[i][j - 1])
				dp[i][j] = dp[i - 1][j], path[i][j] = 2;
			else
				dp[i][j] = dp[i][j - 1], path[i][j] = 3;
		}
  }
	return dp[len1][len2];
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
