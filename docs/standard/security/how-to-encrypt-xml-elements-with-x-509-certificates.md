---
title: "방법: X.509 인증서로 XML 요소 암호화"
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
- encryption [.NET Framework], X.509 certificates
- cryptography [.NET Framework], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6690c87bb7a632a783fc89341d405bf81166470c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="6b114-102">방법: X.509 인증서로 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="6b114-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="6b114-103"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="6b114-104">XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="6b114-105">XML 암호화 표준에 대한 자세한 내용은 http://www.w3.org/TR/xmldsig-core/에 있는 XML 암호화에 대한 W3C(World Wide Web 컨소시엄) 사양을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b114-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at http://www.w3.org/TR/xmldsig-core/.</span></span>  
  
 <span data-ttu-id="6b114-106">XML 암호화를 사용하여 암호화된 XML 데이터가 포함된 <`EncryptedData`> 요소의 문서나 XML 요소를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="6b114-107"><`EncryptedData`> 요소는 암호화 중에 사용된 키와 프로세스에 대한 정보가 들어 있는 하위 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="6b114-108">XML 암호화를 사용하면 문서에 암호화된 여러 요소가 포함될 수 있고 한 요소가 여러 번 암호화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="6b114-109">이 절차의 코드 예제에서는 나중에 암호 해독 과정에서 사용할 수 있는 다른 여러 하위 요소와 함께 <`EncryptedData`> 요소를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="6b114-110">이 예제에서는 두 키를 사용하여 XML 요소를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-110">This example encrypts an XML element using two keys.</span></span>  <span data-ttu-id="6b114-111">[인증서 생성 도구(Makecert.exe)](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)를 사용하여 테스트 X.509 인증서를 생성하고 인증서 저장소에 인증서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-111">It generates a test X.509 certificate using the [Certificate Creation Tool (Makecert.exe)](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx) and saves the certificate to a certificate store.</span></span>  <span data-ttu-id="6b114-112">그런 다음 예제에서는 프로그래밍 방식으로 인증서를 검색하고 <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> 메서드를 통해 XML 요소를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-112">The example then programmatically retrieves the certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span>  <span data-ttu-id="6b114-113">내부적으로 <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> 메서드는 별도의 세션 키를 만들고 XML 문서를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-113">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="6b114-114">이 메서드는 세션 키를 암호화하고 이를 암호화된 XML과 함께 새 <`EncryptedData`> 요소 내부에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-114">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="6b114-115">XML 요소를 암호 해독하려면 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드를 호출하기만 하면 됩니다. 메서드가 자동으로 저장소에서 X.509 인증서를 검색하고 필요한 암호 해독을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-115">To decrypt the XML element, simply call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="6b114-116">이 절차를 사용하여 암호화된 XML 요소를 암호 해독하는 방법에 대한 자세한 내용은 [방법: X.509 인증서로 XML 요소 암호 해독](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b114-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
 <span data-ttu-id="6b114-117">이 예제는 여러 응용 프로그램이 암호화된 데이터를 공유해야 하거나 응용 프로그램이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="6b114-118">X.509 인증서로 XML 요소를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="6b114-118">To encrypt an XML element with an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="6b114-119">[인증서 생성 도구(Makecert.exe)](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)를 사용하여 테스트 X.509 인증서를 생성하고 로컬 사용자 저장소에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-119">Use the [Certificate Creation Tool (Makecert.exe)](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx) to generate a test X.509 certificate and place it in the local user store.</span></span>  <span data-ttu-id="6b114-120">교환 키를 생성해야 하며 키를 내보낼 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-120">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="6b114-121">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-121">Run the following command:</span></span>  
  
    ```  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2005 -e 01/01/2010 -sky exchange -ss my  
    ```  
  
2.  <span data-ttu-id="6b114-122"><xref:System.Security.Cryptography.X509Certificates.X509Store> 개체를 만들고 초기화하여 현재 사용자 저장소를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-122">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3.  <span data-ttu-id="6b114-123">읽기 전용 모드로 저장소를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-123">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4.  <span data-ttu-id="6b114-124">저장소에 있는 모든 인증서를 사용하여 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection>을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-124">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5.  <span data-ttu-id="6b114-125">저장소에 있는 인증서를 열거하고 해당 이름을 가진 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-125">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="6b114-126">이 예제에서 인증서의 이름은 `"CN=XML_ENC_TEST_CERT"`입니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-126">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6.  <span data-ttu-id="6b114-127">인증서를 찾은 후 저장소를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-127">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7.  <span data-ttu-id="6b114-128">디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-128">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="6b114-129"><xref:System.Xml.XmlDocument> 개체는 암호화할 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-129">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8.  <span data-ttu-id="6b114-130"><xref:System.Xml.XmlDocument> 개체에서 지정된 요소를 찾고 암호화할 요소를 나타내는 <xref:System.Xml.XmlElement> 개체를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-130">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="6b114-131">이 예제에서는 `"creditcard"` 요소가 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-131">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="6b114-132"><xref:System.Security.Cryptography.Xml.EncryptedXml> 클래스의 새 인스턴스를 만들고 X.509 인증서를 사용하여 지정된 요소를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-132">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="6b114-133"><xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> 메서드는 암호화된 요소를 <xref:System.Security.Cryptography.Xml.EncryptedData> 개체로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-133">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="6b114-134">원본 <xref:System.Xml.XmlDocument> 개체의 요소를 <xref:System.Security.Cryptography.Xml.EncryptedData> 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-134">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="6b114-135"><xref:System.Xml.XmlDocument> 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-135">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="6b114-136">예제</span><span class="sxs-lookup"><span data-stu-id="6b114-136">Example</span></span>  
 <span data-ttu-id="6b114-137">이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-137">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="6b114-138">또한 `"test.xml"`에 `"creditcard"` 요소가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-138">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="6b114-139">`test.xml`이라는 파일에 다음 XML을 배치하고 이 예제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-139">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b114-140">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6b114-140">Compiling the Code</span></span>  
  
-   <span data-ttu-id="6b114-141">이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-141">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="6b114-142"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-142">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6b114-143">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="6b114-143">.NET Framework Security</span></span>  
 <span data-ttu-id="6b114-144">이 예제에서 사용된 X.509 인증서는 테스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-144">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="6b114-145">응용 프로그램은 신뢰할 수 있는 인증 기관에서 생성된 X.509 인증서를 사용하거나 Microsoft Windows 인증서 서버에서 생성된 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b114-145">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b114-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b114-146">See Also</span></span>  
 <xref:System.Security.Cryptography.Xml>  
 [<span data-ttu-id="6b114-147">방법: X.509 인증서로 XML 요소 해독</span><span class="sxs-lookup"><span data-stu-id="6b114-147">How to: Decrypt XML Elements with X.509 Certificates</span></span>](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md)
