---
title: XML 리터럴의 공백(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245161"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="0c82e-102">XML 리터럴의 공백(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c82e-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="0c82e-103">Visual Basic 컴파일러를 만들 때 XML 리터럴에서 유효 공백 문자만 포함 된 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="0c82e-104">불필요 한 공백 문자는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="0c82e-105">유효 공백과 무효 공백</span><span class="sxs-lookup"><span data-stu-id="0c82e-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="0c82e-106">만 세 가지 영역에서 XML 리터럴의 공백 문자 사항이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="0c82e-107">특성 값에 있을 때.</span><span class="sxs-lookup"><span data-stu-id="0c82e-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="0c82e-108">요소의 텍스트 콘텐츠 일부가 텍스트에도 다른 문자가 시점과 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="0c82e-109">요소의 텍스트 콘텐츠에 대 한 포함된 식을에 있을 때.</span><span class="sxs-lookup"><span data-stu-id="0c82e-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="0c82e-110">그렇지 않으면 컴파일러를 불필요 한 공백 문자를 처리 하 고에 포함 되지 않습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 리터럴의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="0c82e-111">무효 공백은 리터럴 XML에 포함 하려면 공백을 사용 하 여 리터럴 문자열을 포함 하는 포함 된 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c82e-112">경우는 `xml:space` XML 요소 리터럴에 표시 되는 특성, Visual Basic 컴파일러에서 특성을 포함 합니다 <xref:System.Xml.Linq.XElement> 개체가 아니라이 특성에 컴파일러는 공백 문자를 처리 하는 방법을 변경 하지 않습니다 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0c82e-113">예제</span><span class="sxs-lookup"><span data-stu-id="0c82e-113">Examples</span></span>  
 <span data-ttu-id="0c82e-114">다음 예제에서는 두 개의 XML 요소를 외부 및 내부를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="0c82e-115">두 요소 텍스트 내용에 공백이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="0c82e-116">공백 및 XML 요소가 포함 되어 있으므로 외부 요소에서 공백을 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="0c82e-117">요소의 내부에 공백을 공백 및 텍스트 있기 때문에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="0c82e-118">를 실행 하는 경우이 코드는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c82e-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c82e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c82e-119">See Also</span></span>  
 [<span data-ttu-id="0c82e-120">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="0c82e-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
