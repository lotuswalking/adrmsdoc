我们理解出于对安全的考虑，我们希望启用TLS1.2作为HTTPS的网络协议。 经过测试，以下行动方案在实施后，能够成功让ADRMS服务器使用TLS1.2协议建立连接。

行动方案
===============
Disabling TLS 1.0
If TLS 1.0 is disabled on the AD RMS server you need to force .NET to use TLS 1.2. This requires a registry change on the AD RMS server and an IISRESET.
 
TLS 1.0 and others were disabled on the server. Aed the following and rebooted.
Location: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319
Name:  SchUseStrongCrypto
Type:  DWORD
Value: 1

For more information, please refer: https://docs.microsoft.com/en-us/windows-server/security/tls/tls-registry-settings
