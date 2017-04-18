---
title: "방법: 비대칭 키를 사용하여 XML 요소 해독 | Microsoft Docs"
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
  - "비대칭 키"
  - "해독"
  - "System.Security.Cryptography.EncryptedXml 클래스"
  - "System.Security.Cryptography.RSACryptoServiceProvider 클래스"
  - "XML 암호화"
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 비대칭 키를 사용하여 XML 요소 해독
<xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화 및 암호 해독할 수 있습니다.  XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.  XML 암호화 표준에 대한 자세한 내용은 W3C\(World Wide Web 컨소시엄\) 권장 사항 [XML 서명 구문 및 처리](http://go.microsoft.com/fwlink/?LinkID=136777)\(영문\)를 참조하세요.  
  
 이 절차의 예제에서는 [방법: 비대칭 키를 사용하여 XML 요소 암호화](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)에 설명된 메서드를 사용하여 암호화된 XML 요소를 암호 해독합니다.  \<`EncryptedData`\> 요소를 찾아 암호 해독한 다음 이 요소를 원래의 일반 텍스트 XML 요소로 바꿉니다.  
  
 이 예제에서는 두 키를 사용하여 XML 요소를 암호 해독합니다.  키 컨테이너에서 이전에 생성된 RSA 개인 키를 검색한 다음 RSA 키를 사용하여 \<`EncryptedData`\> 요소의 \<`EncryptedKey`\> 요소에 저장된 세션 키를 암호 해독합니다.  그런 다음 예제에서는 세션 키를 사용하여 XML 요소를 암호 해독합니다.  
  
 이 예제는 여러 응용 프로그램이 암호화된 데이터를 공유해야 하거나 응용 프로그램이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.  
  
### 비대칭 키를 사용하여 XML 요소를 암호 해독하려면  
  
1.  <xref:System.Security.Cryptography.CspParameters> 개체를 만들고 키 컨테이너의 이름을 지정합니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 사용하여 컨테이너에서 이전에 생성된 비대칭 키를 검색합니다.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> 생성자에 <xref:System.Security.Cryptography.CspParameters> 개체를 전달하면 키가 자동으로 키 컨테이너에서 검색됩니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3.  새 <xref:System.Security.Cryptography.Xml.EncryptedXml> 개체를 만들어 문서를 암호 해독합니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4.  암호 해독해야 하는 문서 내의 요소와 RSA 키를 연결하는 키\/이름 매핑을 추가합니다.  문서를 암호화할 때 사용한 것과 동일한 키 이름을 사용해야 합니다.  이 이름은 1단계에서 지정한, 키 컨테이너에서 키를 식별하는 데 사용되는 이름과 별개입니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5.  <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드를 호출하여 \<`EncryptedData`\> 요소를 암호 해독합니다.  이 메서드는 RSA 키를 사용하여 세션 키를 암호 해독하고 자동으로 세션 키를 사용하여 XML 요소를 암호 해독합니다.  또한 자동으로 \<`EncryptedData`\> 요소를 원래의 일반 텍스트로 바꿉니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6.  XML 문서를 저장합니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## 예제  
 이 예제에서는 `test.xml`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.  또한 [방법: 비대칭 키를 사용하여 XML 요소 암호화](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)에 설명된 기술을 사용하여 암호화된 XML 요소가 `test.xml`에 들어 있다고 가정합니다.  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## 코드 컴파일  
  
-   이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.  
  
-   <xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.  
  
## .NET Framework 보안  
 대칭 암호화 키를 일반 텍스트로 저장하거나 컴퓨터 간에 일반 텍스트로 대칭 키를 전송하지 마세요.  또한 비대칭 키 쌍의 개인 키를 일반 텍스트로 저장하거나 전송하지 마세요.  대칭 및 비대칭 암호화 키에 대한 자세한 내용은 [암호화 및 해독용 키 생성](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)을 참조하세요.  
  
 소스 코드에 직접 키를 포함하지 마세요.  포함된 키는 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하거나 메모장과 같은 텍스트 편집기에서 어셈블리를 열어 어셈블리에서 쉽게 읽을 수 있습니다.  
  
 암호화 키를 사용하여 작업이 완료되면 각 바이트를 0으로 설정하거나 관리되는 암호화 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> 메서드를 호출하여 메모리에서 지웁니다.  디버거가 메모리에서 암호화 키를 읽거나 메모리 위치가 디스크에 페이징된 경우 하드 드라이브에서 읽을 수 있는 경우도 있습니다.  
  
## 참고 항목  
 <xref:System.Security.Cryptography.Xml>   
 [방법: 비대칭 키를 사용하여 XML 요소 암호화](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)