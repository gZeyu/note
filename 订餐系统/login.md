1. 用户用密码登录成功后，服务器返回token给客户端
2. 客户端将token保存在本地，发起后续的相关请求时，将token发回给服务器
3. 服务器检查token的有效性，有效则返回数据，若无效，分两种情况： 
	- token错误，这时需要用户重新登录，获取正确的token
	- token过期，这时客户端需要再发起一次认证请求，获取新的token
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5NzY1OTYyOF19
-->