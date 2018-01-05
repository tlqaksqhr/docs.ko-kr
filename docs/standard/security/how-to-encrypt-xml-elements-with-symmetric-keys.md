---
title: "방법: 대칭 키를 사용하여 XML 요소 암호화"
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
- AES algorithm
- cryptography [.NET Framework], symmetric keys
- encryption [.NET Framework], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Advanced Encryption Standard algorithm
- Rijndael
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2130a8c615faefeb49219b9df7e5765f77f4fac8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="9e11c-102">방법: 대칭 키를 사용하여 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="9e11c-102">How to: Encrypt XML Elements with Symmetric Keys</span></span>
<span data-ttu-id="9e11c-103"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="9e11c-104">XML 암호화를 사용하면 데이터가 쉽게 읽혀질 염려 없이 중요한 XML을 저장하거나 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="9e11c-105">이 절차에서는 Rijndael이라고도 하는 AES(고급 암호화 표준) 알고리즘을 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-105">This procedure decrypts an XML element using the Advanced Encryption Standard (AES) algorithm, also known as Rijndael.</span></span>  
  
 <span data-ttu-id="9e11c-106">이 절차를 사용 하 여 암호화 된 XML 요소 암호 해독 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 대칭 키로 XML 요소 암호 해독](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-106">For information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Symmetric Keys](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="9e11c-107">AES와 같은 대칭 알고리즘을 사용하여 XML 데이터를 암호화하는 경우 동일한 키를 사용하여 XML 데이터를 암호화하고 암호 해독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="9e11c-108">이 절차의 예제에서는 동일한 키를 사용하여 암호화된 XML이 암호 해독되며 암호화 및 암호 해독하는 당사자가 알고리즘 및 사용할 키에 대해 동의한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-108">The example in this procedure assumes that the encrypted XML will be decrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="9e11c-109">이 예제에서는 암호화된 XML 내의 AES 키를 저장하거나 암호화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="9e11c-110">이 예제는 단일 응용 프로그램에서 메모리에 저장된 세션 키 또는 암호에서 파생된 강력한 암호화 키를 기반으로 하여 데이터를 암호화해야 하는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="9e11c-111">둘 이상의 응용 프로그램에서 암호화된 XML 데이터를 공유해야 하는 경우 비대칭 알고리즘 또는 X.509 인증서를 기반으로 하는 암호화 체계를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="9e11c-112">대칭 키를 사용하여 XML 요소를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="9e11c-112">To encrypt an XML element with a symmetric key</span></span>  
  
1.  <span data-ttu-id="9e11c-113"><xref:System.Security.Cryptography.RijndaelManaged> 클래스를 사용하여 대칭 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-113">Generate a symmetric key using the <xref:System.Security.Cryptography.RijndaelManaged> class.</span></span>  <span data-ttu-id="9e11c-114">이 키는 XML 요소를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-114">This key will be used to encrypt the XML element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2.  <span data-ttu-id="9e11c-115">디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="9e11c-116"><xref:System.Xml.XmlDocument> 개체는 암호화할 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3.  <span data-ttu-id="9e11c-117"><xref:System.Xml.XmlDocument> 개체에서 지정된 요소를 찾고 암호화할 요소를 나타내는 <xref:System.Xml.XmlElement> 개체를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-117">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="9e11c-118">이 예제에서는 `"creditcard"` 요소가 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-118">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4.  <span data-ttu-id="9e11c-119"><xref:System.Security.Cryptography.Xml.EncryptedXml> 클래스의 새 인스턴스를 만들고 대칭 키를 사용하여 <xref:System.Xml.XmlElement>를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-119">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the <xref:System.Xml.XmlElement> with the symmetric key.</span></span>  <span data-ttu-id="9e11c-120"><xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> 메서드는 암호화된 요소를 암호화된 바이트 배열로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-120">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5.  <span data-ttu-id="9e11c-121"><xref:System.Security.Cryptography.Xml.EncryptedData> 개체를 생성하고 XML 암호화 요소의 URL 식별자로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-121">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the XML Encryption element.</span></span>  <span data-ttu-id="9e11c-122">이 URL 식별자를 통해 암호 해독하는 당사자가 XML에 암호화된 요소가 들어 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-122">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="9e11c-123"><xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> 필드를 사용하여 URL 식별자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-123">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6.  <span data-ttu-id="9e11c-124">키를 생성하는 데 사용되는 암호화 알고리즘의 URL 식별자로 초기화되는 <xref:System.Security.Cryptography.Xml.EncryptionMethod> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-124">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the key.</span></span>  <span data-ttu-id="9e11c-125"><xref:System.Security.Cryptography.Xml.EncryptionMethod> 개체를 <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> 속성에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-125">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7.  <span data-ttu-id="9e11c-126"><xref:System.Security.Cryptography.Xml.EncryptedData> 개체에 암호화된 요소 데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-126">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8.  <span data-ttu-id="9e11c-127">원본 <xref:System.Xml.XmlDocument> 개체의 요소를 <xref:System.Security.Cryptography.Xml.EncryptedData> 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-127">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="9e11c-128">예</span><span class="sxs-lookup"><span data-stu-id="9e11c-128">Example</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e11c-129">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9e11c-129">Compiling the Code</span></span>  
  
-   <span data-ttu-id="9e11c-130">이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-130">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="9e11c-131"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-131">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9e11c-132">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="9e11c-132">.NET Framework Security</span></span>  
 <span data-ttu-id="9e11c-133">암호화 키를 일반 텍스트로 저장하거나 컴퓨터 간에 일반 텍스트로 키를 전송하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9e11c-133">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  <span data-ttu-id="9e11c-134">대신, 보안 키 컨테이너를 사용하여 암호화 키를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-134">Instead, use a secure key container to store cryptographic keys.</span></span>  
  
 <span data-ttu-id="9e11c-135">암호화 키를 사용하여 작업이 완료되면 각 바이트를 0으로 설정하거나 관리되는 암호화 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> 메서드를 호출하여 메모리에서 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="9e11c-135">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e11c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e11c-136">See Also</span></span>  
 <xref:System.Security.Cryptography.Xml>  
 [<span data-ttu-id="9e11c-137">방법: 대칭 키를 사용하여 XML 요소 암호 해독</span><span class="sxs-lookup"><span data-stu-id="9e11c-137">How to: Decrypt XML Elements with Symmetric Keys</span></span>](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md)
