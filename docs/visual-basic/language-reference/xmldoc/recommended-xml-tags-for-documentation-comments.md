---
title: "문서 주석 (Visual Basic)에 대 한 권장 XML 태그 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
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
ms.openlocfilehash: e4a6c3128a69e8d666d44882ef3eac9f9a31a51a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="08742-102">문서 주석에 대한 권장 XML 태그(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08742-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="08742-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 XML 파일에 코드의 문서 주석 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08742-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="08742-104">문서에 XML 파일을 처리 하려면 추가 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08742-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="08742-105">XML 주석 형식 등과 같은 코드 구문에 대 한 허용 하 고 멤버를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08742-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="08742-106">부분 형식에 대 한 형식의 일부에 지나지 포함할 수 XML 주석, 있지만 해당 멤버의 주석 처리에 대 한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08742-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08742-107">문서 주석 네임 스페이스에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08742-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="08742-108">이유는 하나의 네임 스페이스가 여러 어셈블리에 걸쳐 있을 수 모든 어셈블리를 동시에 로드할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08742-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="08742-109">컴파일러는 유효한 XML 태그를 모두 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="08742-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="08742-110">다음과 같은 태그는 사용자 설명서에서 자주 사용 되는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08742-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="08742-111">\<c ></span><span class="sxs-lookup"><span data-stu-id="08742-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="08742-112">\<코드 ></span><span class="sxs-lookup"><span data-stu-id="08742-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="08742-113">\<예제 ></span><span class="sxs-lookup"><span data-stu-id="08742-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="08742-114">[\<예외 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="08742-115">[\<포함 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="08742-116">\<list></span><span class="sxs-lookup"><span data-stu-id="08742-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="08742-117">\<p a r a ></span><span class="sxs-lookup"><span data-stu-id="08742-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="08742-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="08742-119">\<paramref ></span><span class="sxs-lookup"><span data-stu-id="08742-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="08742-120">[\<사용 권한 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="08742-121">\<설명 ></span><span class="sxs-lookup"><span data-stu-id="08742-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="08742-122">\<반환 ></span><span class="sxs-lookup"><span data-stu-id="08742-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="08742-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="08742-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="08742-125">\<요약 ></span><span class="sxs-lookup"><span data-stu-id="08742-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="08742-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08742-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="08742-127">\<값 ></span><span class="sxs-lookup"><span data-stu-id="08742-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="08742-128">(<sup>1</sup> 는 컴파일러가 구문을 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="08742-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08742-129">사용 하 여 꺾쇠 괄호 문서 주석의 텍스트를 원한다 면 `<` 및 `>`합니다.</span><span class="sxs-lookup"><span data-stu-id="08742-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="08742-130">예를 들어, 문자열 `"<text in angle brackets>"` 로 나타납니다 `<text in angle``brackets>`합니다.</span><span class="sxs-lookup"><span data-stu-id="08742-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08742-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08742-131">See Also</span></span>  
 <span data-ttu-id="08742-132">[XML 사용 하 여 코드 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="08742-132">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="08742-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="08742-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="08742-134"> [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="08742-134"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
