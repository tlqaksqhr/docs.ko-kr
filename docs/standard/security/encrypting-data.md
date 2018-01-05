---
title: "데이터 암호화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3665ce281fd6426e235aef58448b2cfe46299bd7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="encrypting-data"></a>데이터 암호화
대칭 암호화와 비대칭 암호화는 서로 다른 프로세스를 사용하여 수행됩니다. 대칭 암호화는 스트림에서 수행되므로 많은 양의 데이터를 암호화하는 데 유용합니다. 비대칭 암호화는 적은 수의 바이트에서 수행되므로 적은 양의 데이터에만 유용합니다.  
  
## <a name="symmetric-encryption"></a>대칭 암호화  
 관리되는 대칭 암호화 클래스는 읽은 데이터를 스트림으로 암호화하는 <xref:System.Security.Cryptography.CryptoStream> 이라는 특수 스트림 클래스와 함께 사용됩니다. **CryptoStream** 클래스는 관리되는 스트림 클래스, 암호화 알고리즘을 구현하는 클래스에서 만든 <xref:System.Security.Cryptography.ICryptoTransform> () 인터페이스를 구현하는 클래스 및 <xref:System.Security.Cryptography.CryptoStreamMode> CryptoStream **에 허용되는 액세스 형식을 설명하는**열거형을 사용하여 초기화됩니다. **,** 및 <xref:System.IO.Stream> 을 포함하여 <xref:System.IO.FileStream>클래스에서 파생되는 클래스를 사용하여 <xref:System.IO.MemoryStream>CryptoStream <xref:System.Net.Sockets.NetworkStream>클래스를 초기화할 수 있습니다. 이러한 클래스를 사용하여 다양한 스트림 개체에 대해 대칭 암호화를 수행할 수 있습니다.  
  
 다음 예제에서는 Rijndael 암호화 알고리즘을 구현하는 <xref:System.Security.Cryptography.RijndaelManaged> 의 새 인스턴스를 만들고 **CryptoStream** 클래스에서 암호화를 수행하는 데 사용하는 방법을 보여 줍니다. 이 예제에서 **CryptoStream** 은 임의 형식의 관리되는 스트림일 수 있는 `MyStream` 이라는 스트림 개체를 사용하여 초기화됩니다. **RijndaelManaged** 클래스의 **CreateEncryptor** 메서드에는 암호화에 사용되는 키 및 IV가 전달됩니다. 이 경우 `RMCrypto` 에서 생성되는 기본 키 및 IV가 사용됩니다. 끝으로, **CryptoStreamMode.Write** 가 전달되어 스트림에 대한 쓰기 권한을 지정합니다.  
  
```vb  
Dim RMCrypto As New RijndaelManaged()  
Dim CryptStream As New CryptoStream(MyStream, RMCrypto.CreateEncryptor(RMCrypto.Key, RMCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged RMCrypto = new RijndaelManaged();  
CryptoStream CryptStream = new CryptoStream(MyStream, RMCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 이 코드를 실행하면 **CryptoStream** 개체에 기록된 모든 데이터가 Rijndael 알고리즘을 사용하여 암호화됩니다.  
  
 다음 예제에서는 스트림을 만들고, 스트림을 암호화하고, 스트림에 쓰고, 스트림을 닫는 전체 프로세스를 보여 줍니다. 이 예제에서는 **CryptoStream** 클래스 및 **RijndaelManaged** 클래스를 사용하여 암호화된 네트워크 스트림을 만듭니다. <xref:System.IO.StreamWriter> 클래스를 사용하여 암호화된 스트림에 메시지가 기록됩니다.  
  
> [!NOTE]
>  이 예제를 사용하여 파일에 쓸 수도 있습니다. 이렇게 하려면 <xref:System.Net.Sockets.TcpClient> 참조를 삭제하고 <xref:System.Net.Sockets.NetworkStream> 을 <xref:System.IO.FileStream>으로 바꿉니다.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the   
      'listening process.   
      Dim TCP As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.   
      Dim NetStream As NetworkStream = TCP.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim RMCrypto As New RijndaelManaged()  
  
            Dim Key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim IV As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt   
      'it with the Rijndael class.  
      Dim CryptStream As New CryptoStream(NetStream, RMCrypto.CreateEncryptor(Key, IV), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the   
      'network stream.  
      Dim SWriter As New StreamWriter(CryptStream)  
  
      'Write to the stream.  
      SWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      SWriter.Close()  
      CryptStream.Close()  
      NetStream.Close()  
      TCP.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the   
         //listening process.    
         TcpClient TCP = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.   
         NetworkStream NetStream = TCP.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged RMCrypto = new RijndaelManaged();  
  
         byte[] Key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] IV = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt   
         //it with the Rijndael class.  
         CryptoStream CryptStream = new CryptoStream(NetStream,   
         RMCrypto.CreateEncryptor(Key, IV),     
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the   
         //network stream.  
         StreamWriter SWriter = new StreamWriter(CryptStream);  
  
         //Write to the stream.  
         SWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         SWriter.Close();  
         CryptStream.Close();  
         NetStream.Close();  
         TCP.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 이전 예제가 성공적으로 실행되려면 <xref:System.Net.Sockets.TcpClient> 클래스에 지정된 IP 주소 및 포트 번호에서 수신 대기하는 프로세스가 있어야 합니다. 수신 대기 프로세스가 있는 경우 코드가 수신 대기 프로세스에 연결하고, Rijndael 대칭 알고리즘을 사용하여 스트림을 암호화하며, 스트림에 "Hello World!"를 씁니다. 코드가 성공하면 콘솔에 다음 텍스트가 표시됩니다.  
  
```  
The message was sent.  
```  
  
 그러나 수신 대기 프로세스가 없거나 예외가 발생하는 경우 코드가 콘솔에 다음 텍스트를 표시합니다.  
  
```  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a>비대칭 암호화  
 비대칭 알고리즘은 일반적으로 대칭 키 및 IV의 암호화와 같은 적은 양의 데이터를 암호화하는 데 사용됩니다. 일반적으로 비대칭 암호화를 수행하는 개인은 다른 당사자가 생성한 공개 키를 사용합니다. <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스는 이 목적을 위해 .NET Framework에서 제공됩니다.  
  
 다음 예제에서는 공개 키 정보를 사용하여 대칭 키 및 IV를 암호화합니다. 타사의 공개 키를 나타내는 2바이트 배열이 초기화됩니다. <xref:System.Security.Cryptography.RSAParameters> 개체는 이러한 값으로 초기화됩니다. 다음으로 **RSAParameters** 개체 (이 개체가 나타내는 공개 키)로 가져오는 **RSACryptoServiceProvider** 를 사용 하는 <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> 메서드. 끝으로, <xref:System.Security.Cryptography.RijndaelManaged> 클래스에서 만든 개인 키 및 IV가 암호화됩니다. 이 예제에서는 시스템에 128비트 암호화가 설치되어 있어야 합니다.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim PublicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim Exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim EncryptedSymmetricKey() As Byte  
        Dim EncryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim RSAKeyInfo As New RSAParameters()  
  
        'Set RSAKeyInfo to the public key values.   
        RSAKeyInfo.Modulus = PublicKey  
        RSAKeyInfo.Exponent = Exponent  
  
        'Import key parameters into RSA.  
        RSA.ImportParameters(RSAKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        EncryptedSymmetricKey = RSA.Encrypt(RM.Key, False)  
        EncryptedSymmetricIV = RSA.Encrypt(RM.IV, False)  
    End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Security.Cryptography;  
  
class Class1  
{  
   static void Main()  
   {  
      //Initialize the byte arrays to the public key information.  
      byte[] PublicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] Exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] EncryptedSymmetricKey;  
      byte[] EncryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters RSAKeyInfo = new RSAParameters();  
  
      //Set RSAKeyInfo to the public key values.   
      RSAKeyInfo.Modulus = PublicKey;  
      RSAKeyInfo.Exponent = Exponent;  
  
      //Import key parameters into RSA.  
      RSA.ImportParameters(RSAKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged RM = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      EncryptedSymmetricKey = RSA.Encrypt(RM.Key, false);  
      EncryptedSymmetricIV = RSA.Encrypt(RM.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [암호화 및 해독용 키 생성](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
 [데이터 해독](../../../docs/standard/security/decrypting-data.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
