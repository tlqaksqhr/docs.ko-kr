---
title: 선언된 XML 요소 및 특성의 이름(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07666ead0770c8055a62f75cb481648b0c72ef8b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="3b19a-102">선언된 XML 요소 및 특성의 이름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b19a-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="3b19a-103">이 항목에서는 XML 리터럴의 XML 요소 및 특성 이름 지정에 대 한 Visual Basic 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="3b19a-104">Xml 리터럴, 로컬 이름 또는 정규화 된 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="3b19a-105">정규화 된 이름은 XML 네임 스페이스 접두사, 콜론 및 로컬 이름으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="3b19a-106">XML 네임 스페이스 접두사에 대 한 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3b19a-107">규칙</span><span class="sxs-lookup"><span data-stu-id="3b19a-107">Rules</span></span>  
 <span data-ttu-id="3b19a-108">요소 또는 Visual Basic의 특성의 로컬 이름은 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="3b19a-109">네임 스페이스로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-109">It can begin with a namespace.</span></span> <span data-ttu-id="3b19a-110">알파벳 문자 또는 밑줄로 시작 해야 합니다 (`_`).</span><span class="sxs-lookup"><span data-stu-id="3b19a-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="3b19a-111">영문자, 10 진수 숫자, 밑줄, 마침표 (.) 및 하이픈만 포함 해야 합니다 (-).</span><span class="sxs-lookup"><span data-stu-id="3b19a-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="3b19a-112">1, 024 개 이상의 자 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="3b19a-113">이름에 나타나는 콜론 네임 스페이스 구분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="3b19a-114">따라서 특정 이름에 대 한 XML 네임 스페이스 지정에 콜론을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="3b19a-115">또한 다음 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="3b19a-116">XML 1.0 사양에 문자열 "xml" 모든 대문자 변형으로 시작 하는 모든 이름을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="3b19a-117">따라서 해당 프로그램 요소에 대 한 이름 및 특성 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3b19a-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="3b19a-118">이름 길이 지침</span><span class="sxs-lookup"><span data-stu-id="3b19a-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="3b19a-119">명확히 요소의 특성을 식별 하는 동안 한 이름은 최대한 단축 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="3b19a-120">이 코드의 가독성을 높일 수 및 줄 길이 소스 파일 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="3b19a-121">그러나 사용자 이름이 너무 짧아서는 설명 하지는 않습니다 적절 하 게 요소 또는 코드에서 어떻게 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="3b19a-122">이 코드의 가독성을 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-122">This is important for the readability of your code.</span></span> <span data-ttu-id="3b19a-123">다른 사람을 이해 하려고 하거나 자신을 원하는 경우에 쓰고 이때 후 오랫동안 적절 한 요소 이름을 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="3b19a-124">이름에서 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="3b19a-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="3b19a-125">XML 요소 이름은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-125">XML element names are case sensitive.</span></span> <span data-ttu-id="3b19a-126">이 Visual Basic 컴파일러 알파벳 소문자만 다르고 이름은 동일한 두 개의 비교 하 여 해석 다른 이름으로 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="3b19a-127">예를 들어 해석 `ABC` 및 `abc` 각각 별도 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="3b19a-128">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="3b19a-128">XML Namespaces</span></span>  
 <span data-ttu-id="3b19a-129">XML 요소 리터럴를 만들 때 요소 이름에 대 한 XML 네임 스페이스 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="3b19a-130">자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b19a-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b19a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b19a-131">See Also</span></span>  
 [<span data-ttu-id="3b19a-132">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="3b19a-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="3b19a-133">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="3b19a-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
