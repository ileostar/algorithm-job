# 02-算法实现

```ts {2-3|5|all}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
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
