---
title: "방법: 문자열 (Visual Basic)을 구문 분석 | Microsoft 문서"
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
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
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
ms.openlocfilehash: d06a0ca84650a860a7528cefafaa1c3158e5949a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="ad540-102">방법: 문자열 (Visual Basic)을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="ad540-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="ad540-103">이 항목에서는 C#에서 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad540-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad540-104">예제</span><span class="sxs-lookup"><span data-stu-id="ad540-104">Example</span></span>  
 <span data-ttu-id="ad540-105">문자열을 구문 분석할 수 있습니다 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 를 사용 하 여는 `XElement.Parse` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ad540-105">You can parse a string in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using the `XElement.Parse` method.</span></span> <span data-ttu-id="ad540-106">그러나 XML 리터럴 문자열에서 XML을 구문 분석할 것과 동일한 성능 저하가 발생 하지 않기 때문에 다음 코드에 나와 있는 것 처럼 XML 리터럴을 사용 하 여 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="ad540-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="ad540-107">XML 리터럴을 사용하는 경우 XML을 복사하여 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램에 붙여 넣기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad540-107">By using XML literals, you can just copy and paste your XML into your [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad540-108">텍스트의 구문을 분석하거나 텍스트 파일에서 XML 문서를 로드하는 방법은 함수 생성보다 효율적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad540-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="ad540-109">코드에서 XML 트리를 초기화하는 경우 텍스트의 구문을 분석하는 경우보다 함수 생성을 사용하는 경우에 프로세서 시간을 적게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad540-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad540-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad540-110">See Also</span></span>  
 [<span data-ttu-id="ad540-111">(Visual Basic) XML 구문 분석</span><span class="sxs-lookup"><span data-stu-id="ad540-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
