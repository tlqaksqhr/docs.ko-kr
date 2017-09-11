---
title: "방법: Catch 구문 분석 오류 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6065bb7656151392e4a5b7ad1078706284ba5616
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="8a682-102">방법: Catch 구문 분석 오류 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a682-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="8a682-103">이 항목에서는 잘못 구성되었거나 유효하지 않은 XML을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a682-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="8a682-104"><xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a682-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8a682-105">잘못 구성 되었거나 유효 하지 않은 XML에 전달 되 면 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], 내부 <xref:System.Xml.XmlReader>클래스에는 예외가 throw 됩니다.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="8a682-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="8a682-106">와 같은 XML의 구문을 분석 하는 다양 한 메서드 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, 예외를 catch 하지 않습니다; 예외는 응용 프로그램에서 다음 낼 수 있습니다.</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8a682-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="8a682-107">XML 리터럴을 사용하는 경우에는 구문 분석 오류를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a682-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="8a682-108">Visual Basic 컴파일러는 잘못 구성되었거나 유효하지 않은 XML의 오류를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="8a682-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a682-109">예제</span><span class="sxs-lookup"><span data-stu-id="8a682-109">Example</span></span>  
 <span data-ttu-id="8a682-110">다음 코드에서는 유효하지 않은 XML의 구문 분석을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8a682-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="8a682-111">이 코드를 실행하면 다음 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a682-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="8a682-112">예상할 수 있는 예외에 대 한 내용은 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, 및 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>를 throw 하는 메서드를 참조는 <xref:System.Xml.XmlReader>설명서.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8a682-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a682-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a682-113">See Also</span></span>  
 [<span data-ttu-id="8a682-114">(Visual Basic) XML 구문 분석</span><span class="sxs-lookup"><span data-stu-id="8a682-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
