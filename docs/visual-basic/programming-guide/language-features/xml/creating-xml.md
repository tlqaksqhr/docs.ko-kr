---
title: "Visual Basic에서 XML 만들기 | Microsoft 문서"
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
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
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
ms.openlocfilehash: ec45ab4dc7d4c9282d444c00b0b262b3d8dd4da1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="b509a-102">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="b509a-102">Creating XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b509a-103">사용할 수 있도록 *XML 리터럴을* 코드에서 직접.</span><span class="sxs-lookup"><span data-stu-id="b509a-103"> enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="b509a-104">XML 리터럴 구문을 나타내는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체는 XML 1.0 구문을 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="b509a-105">이렇게 하면 보다 쉽게 코드에 동일한 최종 XML 구조 때문에 XML 요소, 문서 및 조각을 프로그래밍 방식으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b509a-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="b509a-106">In This Section</span></span>  
  
|<span data-ttu-id="b509a-107">용어</span><span class="sxs-lookup"><span data-stu-id="b509a-107">Term</span></span>|<span data-ttu-id="b509a-108">정의</span><span class="sxs-lookup"><span data-stu-id="b509a-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="b509a-109">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="b509a-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="b509a-110">XML 리터럴 및 관계를 소개 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>|  
|[<span data-ttu-id="b509a-111">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="b509a-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="b509a-112">XML 리터럴에서는 포함된 식을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="b509a-113">방법: XML 리터럴 만들기</span><span class="sxs-lookup"><span data-stu-id="b509a-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="b509a-114">XML 리터럴을 사용 하 여 코드에서 XML 요소를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="b509a-115">XML 리터럴의 공백</span><span class="sxs-lookup"><span data-stu-id="b509a-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="b509a-116">설명 방식을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 리터럴의 공백 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-116">Describes how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="b509a-117">XML 리터럴 및 XML 1.0 사양</span><span class="sxs-lookup"><span data-stu-id="b509a-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="b509a-118">에 대해 설명 방법의 XML 리터럴 구문 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 1.0 사양과 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-118">Describes how the XML literal syntax in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="b509a-119">방법: XML 리터럴에 식 포함</span><span class="sxs-lookup"><span data-stu-id="b509a-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="b509a-120">콘텐츠를 만드는 런타임 시 XML 리터럴이 포함된 식을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="b509a-121">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="b509a-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="b509a-122">XML 요소 및 특성 이름을 지정 하는 것에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b509a-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b509a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b509a-123">See Also</span></span>  
 [<span data-ttu-id="b509a-124">XML</span><span class="sxs-lookup"><span data-stu-id="b509a-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
