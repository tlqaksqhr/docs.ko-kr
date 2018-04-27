---
title: '방법: 키 컨테이너에 비대칭 키 저장'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: 20
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: eece5dbcab1e81d9f9a2a5dd9e6ed42da108b09c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="7ba2a-102">방법: 키 컨테이너에 비대칭 키 저장</span><span class="sxs-lookup"><span data-stu-id="7ba2a-102">How to: Store Asymmetric Keys in a Key Container</span></span>
<span data-ttu-id="7ba2a-103">비대칭 개인 키는 로컬 컴퓨터에 축자로 저장하거나 일반 텍스트로 저장해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="7ba2a-104">개인 키를 저장해야 하는 경우에는 키 컨테이너를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-104">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="7ba2a-105">키 컨테이너에 대한 자세한 내용은 [컴퓨터 수준 및 사용자 수준 RSA 키 컨테이너 이해](https://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-105">For more information on key containers, see [Understanding Machine-Level and User-Level RSA Key Containers](https://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span></span>  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="7ba2a-106">비대칭 키를 만들어 키 컨테이너에 저장하려면</span><span class="sxs-lookup"><span data-stu-id="7ba2a-106">To create an asymmetric key and save it in a key container</span></span>  
  
1.  <span data-ttu-id="7ba2a-107">새 인스턴스를 만들고는 <xref:System.Security.Cryptography.CspParameters> 클래스 및 키 컨테이너를 호출 하려면 이름을 전달 하는 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>  
  
2.  <span data-ttu-id="7ba2a-108">파생 되는 클래스의 새 인스턴스를 만들고는 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스 (일반적으로 **RSACryptoServiceProvider** 또는 **DSACryptoServiceProvider**) 이전에 만든 전달  **CspParameters** 개체의 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
### <a name="to-delete-the-key-from-a-key-container"></a><span data-ttu-id="7ba2a-109">키 컨테이너에서 키를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="7ba2a-109">To delete the key from a key container</span></span>  
  
1.  <span data-ttu-id="7ba2a-110">**CspParameters** 클래스의 새 인스턴스를 만들고 키 컨테이너에 지정하려는 이름을 **CspParameters.KeyContainerName** 필드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-110">Create a new instance of a **CspParameters** class and pass the name that you want to call the key container to the **CspParameters.KeyContainerName** field.</span></span>  
  
2.  <span data-ttu-id="7ba2a-111">**AsymmetricAlgorithm** 클래스에서 파생된 클래스의 새 인스턴스를 만들고(일반적으로 **RSACryptoServiceProvider** 또는 **DSACryptoServiceProvider**) 이전에 만든 **CspParameters** 개체를 해당 생성자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-111">Create a new instance of a class that derives from the **AsymmetricAlgorithm** class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
3.  <span data-ttu-id="7ba2a-112">**AsymmetricAlgorithm**에서 파생된 클래스의 **PersistKeyInCSP**속성을 **false**(Visual Basic의 경우 **False**)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-112">Set the **PersistKeyInCSP** property of the class that derives from **AsymmetricAlgorithm** to **false** (**False** in Visual Basic).</span></span>  
  
4.  <span data-ttu-id="7ba2a-113">**AsymmetricAlgorithm**에서 파생된 클래스의 **Clear** 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-113">Call the **Clear** method of the class that derives from **AsymmetricAlgorithm**.</span></span> <span data-ttu-id="7ba2a-114">이 메서드는 클래스의 모든 리소스를 해제하고 키 컨테이너를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-114">This method releases all resources of the class and clears the key container.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ba2a-115">예제</span><span class="sxs-lookup"><span data-stu-id="7ba2a-115">Example</span></span>  
 <span data-ttu-id="7ba2a-116">다음 예제에서는 비대칭 키를 만들어 키 컨테이너에 저장하고 나중에 키를 검색하며 컨테이너에서 키를 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-116">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>  
  
 <span data-ttu-id="7ba2a-117">`GenKey_SaveInContainer` 메서드와 `GetKeyFromContainer` 메서드의 해당 코드는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-117">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span>  <span data-ttu-id="7ba2a-118"><xref:System.Security.Cryptography.CspParameters> 개체의 키 컨테이너 이름을 지정하여 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 속성 또는 <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> 속성을 true로 설정한 상태로 <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> 개체에 전달하면 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-118">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to true, the following occurs.</span></span>  <span data-ttu-id="7ba2a-119">지정된 이름의 키 컨테이너가 없는 경우 해당 이름의 키 컨테이너가 만들어지고 키가 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-119">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>  <span data-ttu-id="7ba2a-120">지정된 이름의 키 컨테이너가 있는 경우 컨테이너의 키가 현재 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 개체에 자동으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-120">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>  <span data-ttu-id="7ba2a-121">따라서 `GenKey_SaveInContainer` 메서드의 코드는 첫 번째로 실행되었기 때문에 키를 지속하는 반면, `GetKeyFromContainer` 메서드의 코드는 두 번째로 실행되었기 때문에 키를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba2a-121">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it is run second.</span></span>  
  
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
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ba2a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ba2a-122">See Also</span></span>  
 [<span data-ttu-id="7ba2a-123">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="7ba2a-123">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
 [<span data-ttu-id="7ba2a-124">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="7ba2a-124">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)  
 [<span data-ttu-id="7ba2a-125">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="7ba2a-125">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)  
 [<span data-ttu-id="7ba2a-126">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7ba2a-126">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
