---
title: "&lt;see&gt;(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 065c85ba411794858c8c4d70de0ac1467da1fe56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="4b465-102">&lt;see&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4b465-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4b465-103">구문</span><span class="sxs-lookup"><span data-stu-id="4b465-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b465-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b465-104">Parameters</span></span>  
 <span data-ttu-id="4b465-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="4b465-105">cref = " `member`"</span></span>  
 <span data-ttu-id="4b465-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="4b465-107">컴파일러는 지정된 코드 요소가 있고 출력 XML의 요소 이름에 `member`를 전달하는지 확인합니다. 큰따옴표(“ ”) 안에 *멤버*를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b465-108">설명</span><span class="sxs-lookup"><span data-stu-id="4b465-108">Remarks</span></span>  
 <span data-ttu-id="4b465-109">\<see> 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="4b465-110">참고 항목 부분에 배치할 텍스트를 지정하려면 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="4b465-111">코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들려면 [cref 특성](../../../csharp/programming-guide/xmldoc/cref-attribute.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="4b465-112">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="4b465-113">다음 예제에서는 요약 섹션의 \<see> 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b465-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4b465-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b465-114">See Also</span></span>  
 [<span data-ttu-id="4b465-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4b465-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4b465-116">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="4b465-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
