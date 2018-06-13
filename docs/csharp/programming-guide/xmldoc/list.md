---
title: '&lt;list&gt;(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 768490424403f1235873a681ffba3367e3f128b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337732"
---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="9e6d6-102">&lt;list&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9e6d6-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="9e6d6-103">구문</span><span class="sxs-lookup"><span data-stu-id="9e6d6-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e6d6-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e6d6-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="9e6d6-105">`description`에서 정의되는, 정의할 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="9e6d6-106">글머리 기호 또는 번호 매기기 목록의 항목이나 `term`의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e6d6-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e6d6-107">Remarks</span></span>  
 <span data-ttu-id="9e6d6-108">\<listheader> 블록은 테이블 또는 정의 목록의 머리글 행을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="9e6d6-109">테이블을 정의할 때는 머리글에 용어 항목만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="9e6d6-110">목록의 각 항목은 \<item> 블록을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="9e6d6-111">정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="9e6d6-112">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우 `description` 항목만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="9e6d6-113">목록 또는 테이블에 \<item> 블록을 필요한 개수만큼 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="9e6d6-114">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6d6-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e6d6-115">예</span><span class="sxs-lookup"><span data-stu-id="9e6d6-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9e6d6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e6d6-116">See Also</span></span>  
 [<span data-ttu-id="9e6d6-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9e6d6-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9e6d6-118">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="9e6d6-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
