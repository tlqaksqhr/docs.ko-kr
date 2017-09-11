---
title: "XML 리터럴 (Visual Basic)에 있는 공백을 | Microsoft 문서"
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
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4fc3d30a9c71cbd732597c5e3f32bd01eb489a80
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="f4bb0-102">XML 리터럴의 공백(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4bb0-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="f4bb0-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러를 만들 때 XML 리터럴에서 유효 공백 문자만 포함 한 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object.</span></span> <span data-ttu-id="f4bb0-104">유효 하지 않은 공백 문자는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="f4bb0-105">유효 공백과 무효 공백의 공백</span><span class="sxs-lookup"><span data-stu-id="f4bb0-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="f4bb0-106">XML 리터럴의 공백 문자는 세 영역에서 상당한:</span><span class="sxs-lookup"><span data-stu-id="f4bb0-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="f4bb0-107">특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="f4bb0-108">요소의 텍스트 콘텐츠의 일부인 시점과 텍스트도 다른 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="f4bb0-109">요소의 텍스트 내용에 대 한 포함된 된 식에서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="f4bb0-110">그렇지 않으면 컴파일러에서는으로 무효 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 리터럴에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="f4bb0-111">무효 공백은 리터럴 xml에서을 포함 하려면 공백 리터럴 문자열이 포함 된 포함된 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4bb0-112">하는 경우는 `xml:space` 리터럴, XML 요소에 특성이 표시 되는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서 특성을 포함는 <xref:System.Xml.Linq.XElement>개체가 아니라 추가이 특성은 컴파일러에서 공백을 처리 하는 방법을 변경 되지 않습니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f4bb0-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f4bb0-113">예제</span><span class="sxs-lookup"><span data-stu-id="f4bb0-113">Examples</span></span>  
 <span data-ttu-id="f4bb0-114">다음 예제에서는 외부 및 내부 두 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="f4bb0-115">두 요소에 텍스트 내용에 공백이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="f4bb0-116">공백 및 XML 요소가 포함 된 외부 요소에 공백이 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="f4bb0-117">요소의 내부에서 공백을 공백 및 텍스트를 포함 하므로 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 <span data-ttu-id="f4bb0-118">[!code-vb[VbXMLSamples #&29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f4bb0-118">[!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span></span>  
  
 <span data-ttu-id="f4bb0-119">를 실행 하는 경우이 코드는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4bb0-119">When run, this code displays the following text.</span></span>  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4bb0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4bb0-120">See Also</span></span>  
 [<span data-ttu-id="f4bb0-121">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="f4bb0-121">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
