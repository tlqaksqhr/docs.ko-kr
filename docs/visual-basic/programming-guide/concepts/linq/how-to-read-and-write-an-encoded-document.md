---
title: "방법: 인코딩된 문서 (Visual Basic)를 읽고 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3247af177066e9b50d5028766f99e7bf6589050f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a>방법: 읽기 및 쓰기 인코딩된 문서 (Visual Basic)
인코딩된 XML 문서를 만들려면 추가 하는 <xref:System.Xml.Linq.XDeclaration>XML 트리를 원하는 코드 페이지 이름으로 인코딩을 설정 합니다.</xref:System.Xml.Linq.XDeclaration>  
  
 반환 된 값 <xref:System.Text.Encoding.WebName%2A>은 유효한 값입니다.</xref:System.Text.Encoding.WebName%2A>  
  
 인코딩된 문서를 읽는 경우의 <xref:System.Xml.Linq.XDeclaration.Encoding%2A>속성이 코드 페이지 이름으로 설정 됩니다.</xref:System.Xml.Linq.XDeclaration.Encoding%2A>  
  
 설정한 경우 <xref:System.Xml.Linq.XDeclaration.Encoding%2A>을 유효한 코드 페이지 이름으로 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 지정 된 인코딩을 사용 하 여이 serialize 합니다.</xref:System.Xml.Linq.XDeclaration.Encoding%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 UTF-8 인코딩을 사용하여 문서를 하나 만들고 UTF-16 인코딩을 사용하여 문서를 하나 만든 다음 그런 다음 문서를 로드하고 인코딩을 콘솔에 출력합니다.  
  
```vb  
Console.WriteLine("Creating a document with utf-8 encoding")  
Dim encodedDoc8 As XDocument = _  
        <?xml version='1.0' encoding='utf-8' standalone='yes'?>  
        <Root>Content</Root>   
  
encodedDoc8.Save("EncodedUtf8.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Console.WriteLine("Creating a document with utf-16 encoding")  
Dim encodedDoc16 As XDocument = _  
        <?xml version='1.0' encoding='utf-16' standalone='yes'?>  
        <Root>Content</Root>  
  
encodedDoc16.Save("EncodedUtf16.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc8 As XDocument = XDocument.Load("EncodedUtf8.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc16 As XDocument = XDocument.Load("EncodedUtf16.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName>   
 [고급 LINQ to XML 프로그래밍 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
