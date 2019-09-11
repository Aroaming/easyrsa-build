Certificates
====
[easyrsa](https://github.com/OpenVPN/easy-rsa)签发证书,克隆项目以后，进入easyrsa3文件夹   

1.初始化pki文件

```
```
./easyrsa init-pki
```
```
Confirm removal: 输入 yes  

2.创建根证书

```
./easyrsa build-ca nopass
```
```
```
Common Name (eg: your user, host, or server name) [Easy-RSA CA]:  
例如：签发者为fhyx,则 输入 fhyx  

3.创建Diffie-Hellman

```
```
./easyrsa gen-dh
```
```

4.创建server端xxxxx证书

```
```
./easyrsa build-server-full xxxxx nopass
```
```

5.创建client端xxxxx证书

```
```
./easyrsa build-client-full xxxxx nopass
```
```

完成创建后pki文件下就存在ca.crt，issued存放证书，private存放私钥。  


6、注销证书 
```
./easyrsa revoke xxxxx
```

7、使用openssl验证签发证书  
输入：  
```
```
openssl verify -CAfile ./pki/ca.crt -untrusted ./pki/ca.crt ./pki/issued/server.crt 
```
```
显示 :OK 则表示签发成功  
```
```
./pki/issued/server.crt: OK 
```
```



参考：  
1、[使用easyrsa3来制作证书](https://www.iteye.com/blog/openwrt-2305318)  
2、[Verify a certificate chain using openssl verify](https://stackoverflow.com/questions/25482199/verify-a-certificate-chain-using-openssl-verify)
