---
title: "방법: Catch 구문 분석 오류 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82b7c51aa8d0f9f64094211c56875e6595607c00
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="ea2f8-102">방법: Catch 구문 분석 오류 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea2f8-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="ea2f8-103">이 항목에서는 잘못 구성되었거나 유효하지 않은 XML을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="ea2f8-104">은(는) <xref:System.Xml.XmlReader>를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="ea2f8-105">잘못 구성되었거나 유효하지 않은 XML이 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에 전달되면 기본 <xref:System.Xml.XmlReader> 클래스에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="ea2f8-106">XML의 구문을 분석하는 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>와 같은 다양한 메서드는 예외를 catch하지 않습니다. 예외는 응용 프로그램에 의해 catch될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="ea2f8-107">XML 리터럴을 사용하는 경우에는 구문 분석 오류를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="ea2f8-108">Visual Basic 컴파일러는 잘못 구성되었거나 유효하지 않은 XML의 오류를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea2f8-109">예제</span><span class="sxs-lookup"><span data-stu-id="ea2f8-109">Example</span></span>  
 <span data-ttu-id="ea2f8-110">다음 코드에서는 유효하지 않은 XML의 구문 분석을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-110">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="ea2f8-111">이 코드를 실행하면 다음 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="ea2f8-112"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 및 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> 메서드가 throw할 수 있는 예외에 대한 자세한 내용은 <xref:System.Xml.XmlReader> 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea2f8-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2f8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea2f8-113">See Also</span></span>  
 [<span data-ttu-id="ea2f8-114">XML 구문 분석 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea2f8-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
