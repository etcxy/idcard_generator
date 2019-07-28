# idcard-generator

> 使用 nodejs 生成身份证
> 
> 本工具仅供研究使用，请勿用于违法用途，否则后果自负

## 使用

$> brew install node

$> cd dir

$> npm install

$> node test.js

在线抠图 https://www.gaoding.com/koutu

```javascript
const idcardGenerator = require('idcard-generator');
const config = {
    name: '喵喵喵',
    sex: '女',
    nation: '汉',
    year: '3000',
    mon: '2',
    day: '31',
    org: '喵喵县公安局',
    validTerm: '2014.02.31-2019.02.31',
    addr: '云南省昆明市喵喵区汪汪路呱呱小区5栋1806',
    idn: '111111111111111111',
    avatar: './images/avatar.png'
}
idcardGenerator(config).then(e => {
    fs.writeFile('./output.png', e, err => {
        if (err) {
            console.log(err);
        } else {
            console.log('保存成功');
        }
    })
}).catch(err => {
    console.log('idcard-generator：测试失败\n' + err.stack);
});
```

## 其他

参考项目：[https://github.com/airob0t/idcardgenerator](https://github.com/airob0t/idcardgenerator)
