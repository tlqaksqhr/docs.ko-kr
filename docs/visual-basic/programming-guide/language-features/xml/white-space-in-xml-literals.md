---
title: "XML 리터럴의 공백(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8587abb98fe33ab2c5a0cef6cea76049a00909e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="3fba3-102">XML 리터럴의 공백(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fba3-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="3fba3-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러를 만들 때 XML 리터럴의 공백 문자만 포함 한 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="3fba3-104">유효 하지 않은 공백 문자는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="3fba3-105">중요 하 고 불필요 한 공백</span><span class="sxs-lookup"><span data-stu-id="3fba3-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="3fba3-106">XML 리터럴의 공백 문자는 3 개의 영역에 중요 한 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="3fba3-107">이러한 특성 값에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="3fba3-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="3fba3-108">요소의 텍스트 콘텐츠의 일부인 시점과 텍스트도 다른 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="3fba3-109">요소의 텍스트 내용에 대 한 포함된 된 식에 서로 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="3fba3-110">그렇지 않으면 컴파일러에서는으로 불필요 한 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 리터럴에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="3fba3-111">무효 공백이 xml 리터럴에 포함 하려면 공백 리터럴 문자열이 포함 된 포함된 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fba3-112">경우는 `xml:space` 특성이 XML 요소 리터럴에에 나타날는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에서 특성을 포함 하는 <xref:System.Xml.Linq.XElement> 개체가 아니라이 특성에는 컴파일러에서 공백을 처리 하는 방법을 변경 하지 않습니다 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3fba3-113">예제</span><span class="sxs-lookup"><span data-stu-id="3fba3-113">Examples</span></span>  
 <span data-ttu-id="3fba3-114">다음 예제에서는 외부 및 내부 두 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="3fba3-115">두 요소에 텍스트 내용에 공백이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="3fba3-116">공백 및 XML 요소가 포함 되어 있기 때문에 외부 요소에서 공백을 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="3fba3-117">요소의 내부에서 공백을 기능은 공백 및 텍스트 포함 되어 있기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="3fba3-118">실행 되는 경우이 코드는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fba3-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fba3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fba3-119">See Also</span></span>  
 [<span data-ttu-id="3fba3-120">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="3fba3-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
