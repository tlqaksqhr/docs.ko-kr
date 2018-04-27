---
title: 문서 주석에 대한 권장 XML 태그(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7815d4c9fddc4e760c7495ef7a2509c55141e96e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="80a48-102">문서 주석에 대한 권장 XML 태그(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80a48-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="80a48-103">Visual Basic 컴파일러에는 XML 파일에 코드에서 문서 주석을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="80a48-104">문서에 XML 파일을 처리 하려면 추가 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="80a48-105">XML 주석 형식 등과 같은 코드 구문에서 허용 하 고 멤버를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="80a48-106">부분 형식에 대 한 종류의 한 부분일 뿐 해당 멤버의 주석 처리에 제한이 없으며 있지만 XML 주석을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80a48-107">문서 주석에 네임 스페이스에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="80a48-108">이유는 네임 스페이스가 하나 여러 어셈블리에 확장 수 모든 어셈블리를 동시에 로드할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="80a48-109">컴파일러는 유효한 XML 태그를 모두 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="80a48-110">다음과 같은 태그는 사용자 용 설명 문서에 자주 사용 되는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="80a48-111">\<c></span><span class="sxs-lookup"><span data-stu-id="80a48-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="80a48-112">\<code></span><span class="sxs-lookup"><span data-stu-id="80a48-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="80a48-113">\<example></span><span class="sxs-lookup"><span data-stu-id="80a48-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="80a48-114">[\<예외 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="80a48-115">[\<포함 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="80a48-116">\<list></span><span class="sxs-lookup"><span data-stu-id="80a48-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="80a48-117">\<para></span><span class="sxs-lookup"><span data-stu-id="80a48-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="80a48-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="80a48-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="80a48-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="80a48-120">[\<사용 권한 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="80a48-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="80a48-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="80a48-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="80a48-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="80a48-123">[\<참조 >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="80a48-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="80a48-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="80a48-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="80a48-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80a48-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="80a48-127">\<value></span><span class="sxs-lookup"><span data-stu-id="80a48-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="80a48-128">(<sup>1</sup> 컴파일러 구문을 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="80a48-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80a48-129">꺾쇠 괄호에 문서 주석의 텍스트를 원하는 경우 사용 하 여 `<` 및 `>`합니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="80a48-130">예를 들어 문자열 `"<text in angle brackets>"` 로 표시 됩니다 `<text in angle``brackets>`합니다.</span><span class="sxs-lookup"><span data-stu-id="80a48-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a48-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80a48-131">See Also</span></span>  
 [<span data-ttu-id="80a48-132">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="80a48-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="80a48-133">/doc</span><span class="sxs-lookup"><span data-stu-id="80a48-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="80a48-134">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="80a48-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
