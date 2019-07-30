1.字符串的unicode表示法

2.字符串的遍历器接口

```
for (let codePoint of 'foo') {
  console.log(codePoint)
}
```

4.json.stringify\(\)

\*\*\*\*5.模板字符串

    //原来
    $('#result').append(
      'There are <b>' + basket.count + '</b> ' +
      'items in your basket, ' +
      '<em>' + basket.onSale +
      '</em> are on sale!'
    );

    //新的
    $('#result').append(`
      There are <b>${basket.count}</b> items
       in your basket, <em>${basket.onSale}</em>
      are on sale!
    `);

    //保留换行和空格
    $('#list').html(`
    <ul>
      <li>first</li>
      <li>second</li>
    </ul>
    `);
    //trim()清除空格和换行
    ('#list').html(`
    <ul>
      <li>first</li>
      <li>second</li>
    </ul>
    `.trim());

5.

