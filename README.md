Certificates
====

## Easyrsa Build

build by [OPENVPN-Easyrsa](https://github.com/OpenVPN/easy-rsa)

1.初始化pki文件

```
./easyrsa init-pki
```
2.创建根证书

```
./easyrsa build-ca nopass
```

3.创建server端证书和private key

```
./easyrsa gen-req server nopass
```

4.给server端证书做签名

```
./easyrsa sign server server
```

5.创建Diffie-Hellman

```
./easyrsa gen-dh
```

6.创建client端证书

```
./easyrsa build-client-full client nopass
```
