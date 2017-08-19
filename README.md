# jubi-tiny-api
计算聚币网(jubi.com)私有API的三个参数。

## 聚币API的坑
最终POST请求时，必须注意参数的排序。  

只有以下两种排序是正确的，其余的都返回104错误：  

> signature,nonce,key  

> nonce,singature,key  

总结：nonce参数一定要在key前头

## "食用"方法  

首先初始化实例：    

> jubi=Jubi('公钥','私钥')  

> data = jubi.get_params()  

> requests.post(url='https://www.jubi.com/api/v1/balance/', data=data) 

