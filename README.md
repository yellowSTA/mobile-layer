# mobile-layer screenshot
![alert.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/alert.png)
![confirm.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/confirm.png)
![loading.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/loading.png)
![toast.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/toast.png)
![toptip.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/toptip.png)
![actions.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/actions.png)
![picker.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/picker.png)
![cityPicker.png](https://github.com/yellowSTA/mobile-layer/raw/master/screenshot/cityPicker.png)

# 使用
+ loading
```javascript
$.loading('加载中...',2000)
//提示语，自动消失时间
//如果不设置消失时间，则会一直存在，可以通过 $.hideLoading 来隐藏
$.loading('加载中...')
$.hideLoading()
```
+ toast
```javascript
$.toast('请输入密码',2000)
//如果不传时间参数。默认2000ms自动消失
```

+ confirm
```javascript
//提示语，标题，点击确定的回调，点击取消的回调
$.confirm('确定要删除吗','提示',function(){
    console.log('ok')
},function(){
    console.log('cncle')
})

//如果不想要标题，可以不传
//提示语，点击确定的回调，点击取消的回调
$.confirm('确定要删除吗',function(){
    console.log('ok')
},function(){
    console.log('cncle')
})
```

+ toptip
```javascript
//提示文字，自动消失的时间，样式名
$.toptip('请输入密码',2000,'blue')
//可以省略后两个参数，默认自动消失的时间为2000ms
$.toptip('请输入密码')
```

+ actions
```javascript
$.actions({
    title:'请选择语言',
    onClose: function(){
        console.log('onclose')
    },
    actions:[
        {
            text: '简体中文',
            onClick: function(){
                console.log('简体中文')
            }
        },
        {
            text: '繁体中文',
            onClick: function(){
                console.log('繁体中文')
            }
        },
        {
            text: 'English',
            onClick: function(){
                console.log('English')
            }
        }
        
    ]
})
```

+ modal
```javascript
//自定义有多个操作按钮的弹窗
$.modal({
    title:'请选择', //标题
    text: '想飞上天和太阳肩并肩', //弹窗内容
    buttons: [
        {onClick: function(){console.log('A')}, text: 'A'},
        {onClick: function(){console.log('B')}, text: 'B'},
        {onClick: function(){console.log('C')}, text: 'C'},
    ]
})
```

+ picker
```javascript
//依赖bscroll.js
//要绑定在input，这样才能动态改变值，input设置readonly
$("#picker").picker({
    title:'请选择手机',
    cols: [
        {
            textAlign:'left', //对齐方式
            values: ['赵', '钱', '孙', '李', '周', '吴', '郑', '王']
        },
        {
            textAlign:'center',
            values: ['杰伦', '磊', '明', '小鹏', '燕姿', '菲菲', 'Baby']
        }
    ]
})
```

+ citypicker
```javascript
//城市选择器，请引入address.js，如果有自己的地址库，可以按格式替换
//要绑定在input，这样才能动态改变值，input设置readonly
$("#citypicker").cityPicker()
```