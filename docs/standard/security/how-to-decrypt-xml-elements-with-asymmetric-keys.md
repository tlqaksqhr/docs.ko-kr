---
title: "방법: 비대칭 키를 사용하여 XML 요소 해독"
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
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af0159f20ed8a8b4c174ab07ebccfedd5a8e7f8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="48e6e-102">방법: 비대칭 키를 사용하여 XML 요소 해독</span><span class="sxs-lookup"><span data-stu-id="48e6e-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="48e6e-103"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화 및 암호 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="48e6e-104">XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="48e6e-105">XML 암호화 표준에 대 한 자세한 내용은 World Wide Web Consortium (W3C) 권장 참조 [XML 서명 구문 및 처리](http://go.microsoft.com/fwlink/?LinkID=136777)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](http://go.microsoft.com/fwlink/?LinkID=136777).</span></span>  
  
 <span data-ttu-id="48e6e-106">이 절차의 예제에 설명 된 메서드를 사용 하 여 암호화 된 XML 요소 암호 해독 [하는 방법: 비대칭 키로 XML 요소 암호화](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="48e6e-107"><`EncryptedData`> 요소를 찾아 암호 해독한 다음 이 요소를 원래의 일반 텍스트 XML 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="48e6e-108">이 예제에서는 두 키를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="48e6e-109">키 컨테이너에서 이전에 생성된 RSA 개인 키를 검색한 다음 RSA 키를 사용하여 <`EncryptedData`> 요소의 <`EncryptedKey`> 요소에 저장된 세션 키를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="48e6e-110">그런 다음 예제에서는 세션 키를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="48e6e-111">이 예제는 여러 응용 프로그램이 암호화된 데이터를 공유해야 하거나 응용 프로그램이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="48e6e-112">비대칭 키를 사용하여 XML 요소를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="48e6e-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1.  <span data-ttu-id="48e6e-113"><xref:System.Security.Cryptography.CspParameters> 개체를 만들고 키 컨테이너의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2.  <span data-ttu-id="48e6e-114"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 사용하여 컨테이너에서 이전에 생성된 비대칭 키를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="48e6e-115"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 생성자에 <xref:System.Security.Cryptography.CspParameters> 개체를 전달하면 키가 자동으로 키 컨테이너에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3.  <span data-ttu-id="48e6e-116">새 <xref:System.Security.Cryptography.Xml.EncryptedXml> 개체를 만들어 문서를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4.  <span data-ttu-id="48e6e-117">암호 해독해야 하는 문서 내의 요소와 RSA 키를 연결하는 키/이름 매핑을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="48e6e-118">문서를 암호화할 때 사용한 것과 동일한 키 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="48e6e-119">이 이름은 1단계에서 지정한, 키 컨테이너에서 키를 식별하는 데 사용되는 이름과 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5.  <span data-ttu-id="48e6e-120"><xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드를 호출하여 <`EncryptedData`> 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="48e6e-121">이 메서드는 RSA 키를 사용하여 세션 키를 암호 해독하고 자동으로 세션 키를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="48e6e-122">또한 자동으로 <`EncryptedData`> 요소를 원래의 일반 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6.  <span data-ttu-id="48e6e-123">XML 문서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="48e6e-124">예제</span><span class="sxs-lookup"><span data-stu-id="48e6e-124">Example</span></span>  
 <span data-ttu-id="48e6e-125">이 예제에서는 `test.xml`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="48e6e-126">또한 있다고 가정 `test.xml` 에 설명 된 기술을 사용 하 여 암호화 된 XML 요소가 포함 되어 [하는 방법: 비대칭 키로 XML 요소 암호화](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="48e6e-127">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="48e6e-127">Compiling the Code</span></span>  
  
-   <span data-ttu-id="48e6e-128">이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="48e6e-129"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="48e6e-130">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="48e6e-130">.NET Framework Security</span></span>  
 <span data-ttu-id="48e6e-131">대칭 암호화 키를 일반 텍스트로 저장하거나 컴퓨터 간에 일반 텍스트로 대칭 키를 전송하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="48e6e-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="48e6e-132">또한 비대칭 키 쌍의 개인 키를 일반 텍스트로 저장하거나 전송하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="48e6e-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="48e6e-133">대칭 및 비대칭 암호화 키에 대 한 자세한 내용은 참조 [암호화 및 암호 해독용 키 생성](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="48e6e-134">소스 코드에 직접 키를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="48e6e-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="48e6e-135">사용 하 여 어셈블리에서 포함 된 키는 쉽게 읽을 수 있습니다 [Ildasm.exe (IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 또는 메모장과 같은 텍스트 편집기에서 어셈블리를 열어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="48e6e-136">암호화 키를 사용하여 작업이 완료되면 각 바이트를 0으로 설정하거나 관리되는 암호화 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> 메서드를 호출하여 메모리에서 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="48e6e-137">디버거가 메모리에서 암호화 키를 읽거나 메모리 위치가 디스크에 페이징된 경우 하드 드라이브에서 읽을 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e6e-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e6e-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48e6e-138">See Also</span></span>  
 <xref:System.Security.Cryptography.Xml>  
 [<span data-ttu-id="48e6e-139">방법: 비대칭 키를 사용하여 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="48e6e-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
