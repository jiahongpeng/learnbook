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


    //大括号里面可以放js表达式，可以运算，可以获取对象属性，可以放方法
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


    //还能嵌套
    const tmpl = addrs => `
      <table>
      ${addrs.map(addr => `
        <tr><td>${addr.first}</td></tr>
        <tr><td>${addr.last}</td></tr>
      `).join('')}
      </table>
    `;

    const data = [
        { first: '<Jane>', last: 'Bond' },
        { first: 'Lars', last: '<Croft>' },
    ];

    console.log(tmpl(data));

6.实例：模板编译

    let template = `
    <ul>
      <% for(let i=0; i < data.supplies.length; i++) { %>
        <li><%= data.supplies[i] %></li>
      <% } %>
    </ul>
    `;


    function compile(template){
      const evalExpr = /<%=(.+?)%>/g;
      const expr = /<%([\s\S]+?)%>/g;

      template = template
        .replace(evalExpr, '`); \n  echo( $1 ); \n  echo(`')
        .replace(expr, '`); \n $1 \n  echo(`');

      template = 'echo(`' + template + '`);';

      let script =
      `(function parse(data){
        let output = "";

        function echo(html){
          output += html;
        }

        ${ template }

        return output;
      })`;

      return script;
    }

    let parse = eval(compile(template));
    div.innerHTML = parse({ supplies: [ "broom", "mop", "cleaner" ] });

7.标签模板\*\*\*\*\*\*不懂

