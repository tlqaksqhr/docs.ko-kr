---
title: "방법: X.509 인증서로 XML 요소 해독"
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
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1ac1f986fdbfe139bdcffc8268fc5fdbf916c936
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="ff684-102">방법: X.509 인증서로 XML 요소 해독</span><span class="sxs-lookup"><span data-stu-id="ff684-102">How to: Decrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="ff684-103"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화 및 암호 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="ff684-104">XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="ff684-105">XML 암호화 표준에 대한 자세한 내용은 http://www.w3.org/TR/xmldsig-core/에 있는 XML 암호화에 대한 W3C(World Wide Web 컨소시엄) 사양을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff684-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at http://www.w3.org/TR/xmldsig-core/.</span></span>  
  
 <span data-ttu-id="ff684-106">이 예제에 설명 된 메서드를 사용 하 여 암호화 된 XML 요소 암호 해독: [하는 방법: X.509 인증서로 XML 요소 암호화](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-106">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="ff684-107"><`EncryptedData`> 요소를 찾아 암호 해독한 다음 이 요소를 원래의 일반 텍스트 XML 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="ff684-108">이 절차의 코드 예제에서는 현재 사용자 계정의 로컬 인증서 저장소에 있는 X.509 인증서를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-108">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="ff684-109">이 예제에서는 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드를 사용하여 X.509 인증서를 자동으로 검색하고 <`EncryptedKey`> 요소의 <`EncryptedData`> 요소에 저장된 세션 키를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-109">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="ff684-110"><xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드는 자동으로 세션 키를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-110">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="ff684-111">이 예제는 여러 응용 프로그램이 암호화된 데이터를 공유해야 하거나 응용 프로그램이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-111">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="ff684-112">X.509 인증서로 XML 요소를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="ff684-112">To decrypt an XML element with an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="ff684-113">디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-113">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="ff684-114"><xref:System.Xml.XmlDocument> 개체는 암호 해독할 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-114">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2.  <span data-ttu-id="ff684-115"><xref:System.Xml.XmlDocument> 개체를 생성자에 전달하여 새 <xref:System.Security.Cryptography.Xml.EncryptedXml>개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-115">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3.  <span data-ttu-id="ff684-116"><xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드를 사용하여 XML 문서를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-116">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4.  <span data-ttu-id="ff684-117"><xref:System.Xml.XmlDocument> 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-117">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ff684-118">예제</span><span class="sxs-lookup"><span data-stu-id="ff684-118">Example</span></span>  
 <span data-ttu-id="ff684-119">이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="ff684-120">또한 `"test.xml"`에 `"creditcard"` 요소가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="ff684-121">`test.xml`이라는 파일에 다음 XML을 배치하고 이 예제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff684-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ff684-122">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ff684-123">이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-123">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="ff684-124"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-124">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ff684-125">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ff684-125">.NET Framework Security</span></span>  
 <span data-ttu-id="ff684-126">이 예제에서 사용된 X.509 인증서는 테스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-126">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="ff684-127">응용 프로그램은 신뢰할 수 있는 인증 기관에서 생성된 X.509 인증서를 사용하거나 Microsoft Windows 인증서 서버에서 생성된 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff684-127">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff684-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff684-128">See Also</span></span>  
 <xref:System.Security.Cryptography.Xml>  
 [<span data-ttu-id="ff684-129">방법: X.509 인증서로 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="ff684-129">How to: Encrypt XML Elements with X.509 Certificates</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)
