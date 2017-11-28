---
title: "방법: 인코딩된 문서 읽기 및 쓰기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a08fa9404c92bd64b07059df2f419bff5f80da3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-and-write-an-encoded-document-c"></a><span data-ttu-id="9140c-102">방법: 인코딩된 문서 읽기 및 쓰기(C#)</span><span class="sxs-lookup"><span data-stu-id="9140c-102">How to: Read and Write an Encoded Document (C#)</span></span>
<span data-ttu-id="9140c-103">인코딩된 XML 문서를 만들려면 <xref:System.Xml.Linq.XDeclaration>을 XML 트리에 추가하여 인코딩을 원하는 코드 페이지 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9140c-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="9140c-104"><xref:System.Text.Encoding.WebName%2A>에서 반환하는 모든 값은 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9140c-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="9140c-105">인코딩된 문서를 읽는 경우 <xref:System.Xml.Linq.XDeclaration.Encoding%2A> 속성이 코드 페이지 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9140c-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="9140c-106"><xref:System.Xml.Linq.XDeclaration.Encoding%2A>을 유효한 코드 페이지 이름으로 설정하는 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 지정된 인코딩을 사용하여 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="9140c-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9140c-107">예제</span><span class="sxs-lookup"><span data-stu-id="9140c-107">Example</span></span>  
 <span data-ttu-id="9140c-108">다음 예제에서는 UTF-8 인코딩을 사용하여 문서를 하나 만들고 UTF-16 인코딩을 사용하여 문서를 하나 만든 다음</span><span class="sxs-lookup"><span data-stu-id="9140c-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="9140c-109">그런 다음 문서를 로드하고 인코딩을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="9140c-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 <span data-ttu-id="9140c-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9140c-110">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9140c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9140c-111">See Also</span></span>  
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9140c-112">고급 LINQ to XML 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="9140c-112">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
