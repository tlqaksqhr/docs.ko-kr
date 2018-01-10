---
title: "암호화 서명"
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
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4e460c11e0e78d56a54da1dd178b3f8e9f381b6
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="cryptographic-signatures"></a>암호화 서명
<a name="top"></a> 암호화 디지털 서명은 public 키 알고리즘을 사용하여 데이터 무결성을 제공합니다. 디지털 서명으로 데이터에 서명하면 다른 사용자가 서명을 확인하고 데이터가 원래 서명자로부터 시작되고 서명자가 서명한 이후 변경되지 않았음을 증명할 수 있습니다. 디지털 서명에 대한 자세한 내용은 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)를 참조하세요.  
  
 이 항목에서는 <xref:System.Security.Cryptography?displayProperty=nameWithType> 네임스페이스의 클래스를 사용하여 디지털 서명을 생성 및 확인하는 방법을 설명합니다.  
  
-   [서명 생성](#generate)  
  
-   [서명 확인](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a>서명 생성  
 일반적으로 디지털 서명은 더 큰 데이터를 나타내는 해시 값에 적용됩니다. 다음 예제에서는 해시 값에 디지털 서명을 적용합니다. 먼저 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스의 새 인스턴스는 public/private 키 쌍을 생성합니다. 다음으로 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 는 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> 클래스의 새 인스턴스에 전달됩니다. 실제로 디지털 서명을 수행하는 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>에 private 키를 전달합니다. 해시 코드에 서명하기 전에 사용할 해시 알고리즘을 지정해야 합니다. 이 예제에서는 SHA1 알고리즘을 사용합니다. 마지막으로 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> 메서드가 호출되어 서명을 수행합니다.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
    Sub Main()  
        'The hash value to sign.  
        Dim HashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}  
  
        'The value to hold the signed value.  
        Dim SignedHashValue() As Byte  
  
        'Generate a public/private key pair.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create an RSAPKCS1SignatureFormatter object and pass it   
        'the RSACryptoServiceProvider to transfer the private key.  
        Dim RSAFormatter As New RSAPKCS1SignatureFormatter(RSA)  
  
        'Set the hash algorithm to SHA1.  
        RSAFormatter.SetHashAlgorithm("SHA1")  
  
        'Create a signature for HashValue and assign it to   
        'SignedHashValue.  
        SignedHashValue = RSAFormatter.CreateSignature(HashValue)  
    End Sub  
End Module  
  
using System;  
using System.Security.Cryptography;  
```  
  
```csharp  
class Class1  
{  
   static void Main()  
   {  
      //The hash value to sign.  
      byte[] HashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};  
  
      //The value to hold the signed value.  
      byte[] SignedHashValue;  
  
      //Generate a public/private key pair.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create an RSAPKCS1SignatureFormatter object and pass it the   
      //RSACryptoServiceProvider to transfer the private key.  
      RSAPKCS1SignatureFormatter RSAFormatter = new RSAPKCS1SignatureFormatter(RSA);  
  
      //Set the hash algorithm to SHA1.  
      RSAFormatter.SetHashAlgorithm("SHA1");  
  
      //Create a signature for HashValue and assign it to   
      //SignedHashValue.  
      SignedHashValue = RSAFormatter.CreateSignature(HashValue);  
   }  
}  
```  
  
### <a name="signing-xml-files"></a>XML 파일에 서명  
 .NET Framework는 XML에 서명하는 데 사용되는 <xref:System.Security.Cryptography.Xml> 네임스페이스를 제공합니다. XML이 특정 소스에서 시작되는지 확인하려면 XML에 서명해야 합니다. 예를 들어 XML을 사용하는 주식 시세 서비스를 이용하고 있다면 서명된 XML의 소스를 확인할 수 있습니다.  
  
 이 네임 스페이스의 클래스에 따라는 [XML 서명 구문 및 처리 권장 사항](http://www.w3.org/TR/xmldsig-core/) World Wide Web Consortium에서 합니다.  
  
 [맨 위로 이동](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a>서명 확인  
 특정 당사자가 데이터에 서명했는지 확인하려면 다음 정보가 있어야 합니다.  
  
-   데이터에 서명한 당사자의 public 키입니다.  
  
-   디지털 서명입니다.  
  
-   서명된 데이터입니다.  
  
-   서명자가 사용한 해시 알고리즘입니다.  
  
 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> 클래스로 서명된 서명을 확인하려면 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 클래스를 사용합니다. <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 클래스에는 서명자의 public 키가 제공되어야 합니다. public 키를 지정하려면 모듈러스 및 지수의 값이 필요합니다. public/private 키 쌍을 생성한 당사자가 이들 값을 제공해야 합니다. 먼저 만듭니다는 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 가 서명을 확인 한 다음 초기화 공개 키를 보유 하는 개체는 <xref:System.Security.Cryptography.RSAParameters> 구조체를 공개 키를 지정 하는 모듈러스 및 지 수 값입니다.  
  
 다음 코드는 <xref:System.Security.Cryptography.RSAParameters> 구조체를 만드는 방법을 보여 줍니다. `Modulus` 속성은 `ModulusData` 바이트 배열 값으로 설정되고 `Exponent` 속성은 `ExponentData`바이트 배열 값으로 설정됩니다.  
  
```vb  
Dim RSAKeyInfo As RSAParameters  
RSAKeyInfo.Modulus = ModulusData  
RSAKeyInfo.Exponent = ExponentData  
```  
  
```csharp  
RSAParameters RSAKeyInfo;  
RSAKeyInfo.Modulus = ModulusData;  
RSAKeyInfo.Exponent = ExponentData;  
```  
  
 <xref:System.Security.Cryptography.RSAParameters> 개체를 만든 후에 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스의 새 인스턴스를 <xref:System.Security.Cryptography.RSAParameters>에 지정된 값으로 초기화할 수 있습니다. <xref:System.Security.Cryptography.RSACryptoServiceProvider> 가 다시 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 의 생성자에 전달되어 키를 전송합니다.  
  
 다음 예제에서는 이 프로세스를 보여 줍니다. 이 예제에서 `HashValue` 및 `SignedHashValue` 는 원격 당사자가 제공한 바이트 배열입니다. 원격 당사자는 `HashValue` 를 생성하는 SHA1 알고리즘을 사용하여 `SignedHashValue`에 서명했습니다. Component  
  
 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> 메서드는 디지털 서명이 유효하고 `HashValue`에 서명하는 데 사용되었는지 확인합니다.  
  
```vb  
Dim RSA As New RSACryptoServiceProvider()  
RSA.ImportParameters(RSAKeyInfo)  
Dim RSADeformatter As New RSAPKCS1SignatureDeformatter(RSA)  
RSADeformatter.SetHashAlgorithm("SHA1")  
If RSADeformatter.VerifySignature(HashValue, SignedHashValue) Then  
   Console.WriteLine("The signature is valid.")  
Else  
   Console.WriteLine("The signture is not valid.")  
End If  
```  
  
```csharp  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
RSA.ImportParameters(RSAKeyInfo);  
RSAPKCS1SignatureDeformatter RSADeformatter = new RSAPKCS1SignatureDeformatter(RSA);  
RSADeformatter.SetHashAlgorithm("SHA1");  
if(RSADeformatter.VerifySignature(HashValue, SignedHashValue))  
{  
   Console.WriteLine("The signature is valid.");  
}  
else  
{  
   Console.WriteLine("The signature is not valid.");  
}  
```  
  
 이 코드 조각은 서명이 유효하면 "`The signature is valid`"를 표시하고, 유효하지 않으면 "`The signature is not valid`"를 표시합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
