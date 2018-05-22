---
title: 문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 54047746db672efbf626eb2d3fc301b341cc49f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="5057d-102">문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5057d-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="5057d-103">C# 컴파일러는 코드의 문서 주석을 처리하고 **/doc** 명령줄 옵션에서 지정한 이름의 파일에 XML로 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="5057d-104">컴파일러에서 생성한 파일을 기반으로 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="5057d-105">태그는 형식, 형식 멤버 등의 코드 구문에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5057d-106">네임스페이스에는 문서 주석을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="5057d-107">컴파일러는 유효한 XML인 태그를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="5057d-108">다음 태그는 사용자 문서에서 일반적으로 사용되는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="5057d-109">Tags</span><span class="sxs-lookup"><span data-stu-id="5057d-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="5057d-110">\<c></span><span class="sxs-lookup"><span data-stu-id="5057d-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="5057d-111">\<para></span><span class="sxs-lookup"><span data-stu-id="5057d-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="5057d-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span></span>|  
|[<span data-ttu-id="5057d-113">\<code></span><span class="sxs-lookup"><span data-stu-id="5057d-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="5057d-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span></span>|<span data-ttu-id="5057d-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span></span>|  
|[<span data-ttu-id="5057d-116">\<example></span><span class="sxs-lookup"><span data-stu-id="5057d-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="5057d-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="5057d-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="5057d-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="5057d-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="5057d-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span></span>|<span data-ttu-id="5057d-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span></span>|<span data-ttu-id="5057d-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span></span>|  
|<span data-ttu-id="5057d-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span><span class="sxs-lookup"><span data-stu-id="5057d-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span></span>|[<span data-ttu-id="5057d-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="5057d-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="5057d-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="5057d-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="5057d-125">\<list></span><span class="sxs-lookup"><span data-stu-id="5057d-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="5057d-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="5057d-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="5057d-127">\<value></span><span class="sxs-lookup"><span data-stu-id="5057d-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="5057d-128">(\* 컴파일러에서 구문을 확인함을 나타냅니다.)</span><span class="sxs-lookup"><span data-stu-id="5057d-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="5057d-129">문서 주석의 텍스트에 꺾쇠 괄호를 표시하려면 다음 예제와 같이 `<` 및 `>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5057d-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5057d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5057d-130">See Also</span></span>  
 [<span data-ttu-id="5057d-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5057d-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5057d-132">/doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="5057d-132">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="5057d-133">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="5057d-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
