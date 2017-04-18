---
title: "방법: 키 컨테이너에 비대칭 키 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "비대칭 키[.NET Framework]"
  - "암호화[.NET Framework], 비대칭 키"
  - "해독 키"
  - "암호화[.NET Framework], 비대칭 키"
  - "암호화 키"
  - "keys, 비대칭"
  - "keys, 키 컨테이너에 저장"
  - "비대칭 키 저장"
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 키 컨테이너에 비대칭 키 저장
비대칭 개인 키는 로컬 컴퓨터에 축자로 저장하거나 일반 텍스트로 저장해서는 안 됩니다.  개인 키를 저장해야 하는 경우에는 키 컨테이너를 사용해야 합니다.  키 컨테이너에 대한 자세한 내용은 [Understanding Machine\-Level and User\-Level RSA Key Containers](../Topic/Understanding%20Machine-Level%20and%20User-Level%20RSA%20Key%20Containers.md)를 참조하세요.  
  
### 비대칭 키를 만들어 키 컨테이너에 저장하려면  
  
1.  <xref:System.Security.Cryptography.CspParameters> 클래스의 새 인스턴스를 만들고 키 컨테이너에 지정하려는 이름을 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=fullName> 필드에 전달합니다.  
  
2.  <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스에서 파생된 클래스의 새 인스턴스를 만들고\(일반적으로 **RSACryptoServiceProvider** 또는 **DSACryptoServiceProvider**\) 이전에 만든 **CspParameters** 개체를 해당 생성자에 전달합니다.  
  
### 키 컨테이너에서 키를 삭제하려면  
  
1.  **CspParameters** 클래스의 새 인스턴스를 만들고 키 컨테이너에 지정하려는 이름을 **CspParameters.KeyContainerName** 필드에 전달합니다.  
  
2.  **AsymmetricAlgorithm** 클래스에서 파생된 클래스의 새 인스턴스를 만들고\(일반적으로 **RSACryptoServiceProvider** 또는 **DSACryptoServiceProvider**\) 이전에 만든 **CspParameters** 개체를 해당 생성자에 전달합니다.  
  
3.  **AsymmetricAlgorithm**에서 파생된 클래스의 **PersistKeyInCSP** 속성을 **false**\(Visual Basic의 경우 **False**\)로 설정합니다.  
  
4.  **AsymmetricAlgorithm**에서 파생된 클래스의 **Clear** 메서드를 호출합니다.  이 메서드는 클래스의 모든 리소스를 해제하고 키 컨테이너를 지웁니다.  
  
## 예제  
 다음 예제에서는 비대칭 키를 만들어 키 컨테이너에 저장하고 나중에 키를 검색하며 컨테이너에서 키를 삭제하는 방법을 보여 줍니다.  
  
 `GenKey_SaveInContainer` 메서드와 `GetKeyFromContainer` 메서드의 해당 코드는 유사합니다.  <xref:System.Security.Cryptography.CspParameters> 개체의 키 컨테이너 이름을 지정하여 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 속성 또는 <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> 속성을 true로 설정한 상태로 <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> 개체에 전달하면 다음과 같은 상황이 발생합니다.  지정된 이름의 키 컨테이너가 없는 경우 해당 이름의 키 컨테이너가 만들어지고 키가 지속됩니다.  지정된 이름의 키 컨테이너가 있는 경우 컨테이너의 키가 현재 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 개체에 자동으로 로드됩니다.  따라서 `GenKey_SaveInContainer` 메서드의 코드는 첫 번째로 실행되었기 때문에 키를 지속하는 반면, `GetKeyFromContainer` 메서드의 코드는 두 번째로 실행되었기 때문에 키를 로드합니다.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```Output  
  
            컨테이너에 추가된 키:  
<RSAKeyValue> 키 정보 A</RSAKeyValue>  
컨테이너에서 검색된 키:  
<RSAKeyValue> 키 정보 A</RSAKeyValue>  
키가 삭제되었습니다.  컨테이너에 추가된 키:  
<RSAKeyValue> 키 정보 B</RSAKeyValue>  
키가 삭제되었습니다.    
```  
  
## 참고 항목  
 [암호화 및 해독용 키 생성](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)   
 [데이터 암호화](../../../docs/standard/security/encrypting-data.md)   
 [데이터 해독](../../../docs/standard/security/decrypting-data.md)   
 [암호화 서비스](../../../docs/standard/security/cryptographic-services.md)