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
    //嵌入变量需要写在${}中
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
    //trim()清除空格和换行//从字符串中移除前导空格、尾随空格和行终止符。
    ('#list').html(`
    <ul>
      <li>first</li>
      <li>second</li>
    </ul>
    `.trim());


    //
    let x = 1;
    let y = 2;

    `${x} + ${y} = ${x + y}`
    // "1 + 2 = 3"

    `${x} + ${y * 2} = ${x + y * 2}`
    // "1 + 4 = 5"

    let obj = {x: 1, y: 2};
    `${obj.x + obj.y}`
    // "3"
    function fn() {
      return "Hello World";
    }

    `foo ${fn()} bar`
    // foo Hello World bar

6.

