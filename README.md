# 官方安卓星云钱包（nasnano）接入文档
## (测试中，如有问题或建议请及时反馈)

nasnano下载地址：https://nano.nebulas.io/index_cn.html


安卓版本跳转简述
#### 引入androidSDK 
在你的项目工程中引入该项目 

方式实例（其他包依赖管理方式均可）：

下载https://github.com/nebulasio/androidSDK/blob/master/libnebulas-release.aar 

(或自行打包https://github.com/nebulasio/androidSDK/edit/master/README.md)

（1）将aar包在你项目的libs中

（2）在build.gradle中引入依赖

```
repositories {
    flatDir {
        dir 'libs'
    }
}
```

```
dependencies {
...
+    compile(name: 'libnebulas-release', ext: 'aar')
+    implementation 'com.squareup.okhttp3:okhttp:3.10.0'
+    implementation 'com.google.code.gson:gson:2.8.4'
...
}
```

#### 调用接口 pay
```
        clickButton.setOnClickListener( new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                // TODO Auto-generated method stub

                GoodsModel gm = new GoodsModel();
                gm.name = "mytestGood";       // 商品名称
                gm.desc = "mytestGoodDesp";   //商品描述

                String toAddr = "n1lxxx…………………………";  // 目标地址
                String valueInWei = "your value";    // your value
                SmartContracts.pay(MainActivity.this , gm, toAddr, valueInWei);

            }
        });
```
#### 调用接口 call() 传入参数参考上面
#### 调用接口 queryTransferStatus() 传入id



> 感谢社区小伙伴 大道 提供技术支持

