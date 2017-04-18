---
title: "방법: XML 문서의 디지털 서명 확인 | Microsoft Docs"
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
  - "서명 검사"
  - "디지털 서명, 확인"
  - "서명, 암호화"
  - "System.Security.Cryptography.RSACryptoServiceProvider 클래스"
  - "System.Security.Cryptography.SignedXml 클래스"
  - "서명 확인"
  - "XML 디지털 서명"
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: XML 문서의 디지털 서명 확인
<xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 디지털 서명으로 서명된 XML 데이터를 확인할 수 있습니다.  XML 디지털 서명\(XMLDSIG\)을 사용하면 서명된 후 데이터가 변경되지 않았음을 확인할 수 있습니다.  XMLDSIG 표준에 대한 자세한 내용은 http:\/\/www.w3.org\/TR\/xmldsig\-core\/의 W3C\(World Wide Web 컨소시엄\) 사양을 참조하세요.  
  
 이 절차의 코드 예제에서는 \<`Signature`\> 요소에 포함된 XML 디지털 서명을 확인하는 방법에 대해 설명합니다.  이 예제에서는 키 컨테이너에서 RSA 공개 키를 검색한 다음 키를 사용하여 서명을 확인합니다.  
  
 이 기술을 사용하여 확인할 수 있는 디지털 서명을 만드는 방법에 대한 자세한 내용은 [방법: 디지털 서명으로 XML 문서 서명](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)을 참조하세요.  
  
### XML 문서의 디지털 서명을 확인하려면  
  
1.  문서를 확인하려면 서명에 사용된 것과 동일한 비대칭 키를 사용해야 합니다.  <xref:System.Security.Cryptography.CspParameters> 개체를 만들고 서명에 사용된 키 컨테이너의 이름을 지정합니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스를 사용하여 공개 키를 검색합니다.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스의 생성자에 <xref:System.Security.Cryptography.CspParameters> 개체를 전달하면 키가 이름을 기준으로 자동으로 키 컨테이너에서 로드됩니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3.  디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.  <xref:System.Xml.XmlDocument> 개체에는 확인할 서명된 XML 문서가 들어 있습니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4.  새 <xref:System.Security.Cryptography.Xml.SignedXml> 개체를 만들고 <xref:System.Xml.XmlDocument> 개체를 전달합니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5.  \<`signature`\> 요소를 찾고 새 <xref:System.Xml.XmlNodeList> 개체를 만듭니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6.  첫 번째 \<`signature`\> 요소의 XML을 <xref:System.Security.Cryptography.Xml.SignedXml> 개체에 로드합니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7.  <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> 메서드 및 RSA 공개 키를 사용하여 서명을 확인합니다.  이 메서드는 성공 또는 실패를 나타내는 부울 값을 반환합니다.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## 예제  
 이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.  [방법: 디지털 서명으로 XML 문서 서명](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)에 설명된 기술을 사용하여 `"test.xml"` 파일에 서명해야 합니다.  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## 코드 컴파일  
  
-   이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.  
  
-   <xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.  
  
## .NET Framework 보안  
 비대칭 키 쌍의 개인 키를 일반 텍스트로 저장하거나 전송하지 마세요.  대칭 및 비대칭 암호화 키에 대한 자세한 내용은 [암호화 및 해독용 키 생성](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)을 참조하세요.  
  
 소스 코드에 직접 개인 키를 포함하지 마세요.  포함된 키는 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하거나 메모장과 같은 텍스트 편집기에서 어셈블리를 열어 어셈블리에서 쉽게 읽을 수 있습니다.  
  
## 참고 항목  
 <xref:System.Security.Cryptography.Xml>   
 [방법: 디지털 서명으로 XML 문서 서명](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)