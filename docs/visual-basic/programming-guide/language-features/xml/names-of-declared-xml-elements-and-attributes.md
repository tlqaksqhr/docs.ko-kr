---
title: "선언 된 XML 요소 및 특성 (Visual Basic)의 이름 | Microsoft 문서"
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
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
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
ms.openlocfilehash: 2c0bb2350f50138d00e202e2e887a2202d21942f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="b2359-102">선언된 XML 요소 및 특성의 이름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2359-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="b2359-103">이 항목에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 리터럴의 XML 요소 및 특성 이름을 지정 하는 것에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-103">This topic provides [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="b2359-104">Xml 리터럴, 로컬 이름 또는 정규화 된 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="b2359-105">정규화 된 이름은 XML 네임 스페이스 접두사, 콜론 및 로컬 이름으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="b2359-106">XML 네임 스페이스 접두사에 대 한 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b2359-107">규칙</span><span class="sxs-lookup"><span data-stu-id="b2359-107">Rules</span></span>  
 <span data-ttu-id="b2359-108">요소 또는 특성의 로컬 이름 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-108">A local name of an element or attribute in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="b2359-109">네임 스페이스로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-109">It can begin with a namespace.</span></span> <span data-ttu-id="b2359-110">영문자 또는 밑줄으로 시작 해야 합니다 (`_`).</span><span class="sxs-lookup"><span data-stu-id="b2359-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="b2359-111">알파벳 문자,&10; 진수 숫자, 밑줄, 마침표 (.) 및 하이픈만 포함 해야 합니다 (-).</span><span class="sxs-lookup"><span data-stu-id="b2359-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="b2359-112">개 이상의 1, 024 자 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="b2359-113">이름에 나타나는 콜론 네임 스페이스 구분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="b2359-114">따라서 특정 이름에 대 한 XML 네임 스페이스 지정에 대해서만 콜론을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="b2359-115">또한 다음 지침을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="b2359-116">XML 1.0 사양에는 문자열 "xml" 모든 대문자 변형로 시작 하는 모든 이름을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="b2359-117">따라서 이러한 요소에 대 한 이름과 특성 이름은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b2359-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="b2359-118">이름 길이 지침</span><span class="sxs-lookup"><span data-stu-id="b2359-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="b2359-119">실용적인 문제로 명확히 요소의 특성을 식별 하는 이름은 가능한 한 짧게 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="b2359-120">이 코드의 가독성을 향상 하 고 줄 길이 소스 파일 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="b2359-121">그러나 사용자 이름은 너무 짧아서는 설명 하지는 않습니다 적절 하 게 요소 또는 코드에서 어떻게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="b2359-122">이 코드의 가독성을 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-122">This is important for the readability of your code.</span></span> <span data-ttu-id="b2359-123">다른 사용자가 이해 하려고 하거나 직접 보는 쓰고 후 오랫동안 하는 경우 적절 한 요소 이름을 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="b2359-124">이름에서 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="b2359-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="b2359-125">XML 요소 이름은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-125">XML element names are case sensitive.</span></span> <span data-ttu-id="b2359-126">즉, 해당 경우에는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서는 두 이름이 소문자만 다르고, 서로 다른 이름으로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-126">This means that when the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="b2359-127">예를 들어 해석 `ABC` 및 `abc` 각각 별도 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="b2359-128">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b2359-128">XML Namespaces</span></span>  
 <span data-ttu-id="b2359-129">XML 요소 리터럴를 만들 때 요소 이름에 대 한 XML 네임 스페이스 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="b2359-130">자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2359-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2359-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2359-131">See Also</span></span>  
 <span data-ttu-id="b2359-132">[Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="b2359-132">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="b2359-133"> [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span><span class="sxs-lookup"><span data-stu-id="b2359-133"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span></span>
