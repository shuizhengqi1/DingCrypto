### DingCrypto

该模块主要是用于解决钉钉的消息加密与解密，因为官方并没有提供相关 的sdk，所以将自己的采坑经验分享出来


使用pip进行安装
```
pip install DingCrypto
```


使用方法

```
from DingCrypto import DingCrypto

dingCrypto = DingCrypto(encodingAesKey,key)      ##此处的encodeingAesKey为在注册接口时填写的aes_key,后面的key对于普通企业开发，填写企业的Corpid。对于ISV开发来说，填写对应的suitekey

###生成签名
signature = dingCrypto.generateSignature(nonce, timestamp, token, msg_encrypt)

##加密数据
encrypt = dingCrypto.encrypt(content)

##解密数据
decrypt = dingCrypto.decrypt(content)
```

