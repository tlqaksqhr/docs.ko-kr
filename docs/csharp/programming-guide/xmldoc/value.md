---
title: '&lt;value&gt;(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 22de15560d6db6e8a70cea744dd9d85359336306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="637d6-102">&lt;value&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="637d6-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="637d6-103">구문</span><span class="sxs-lookup"><span data-stu-id="637d6-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="637d6-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="637d6-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="637d6-105">속성에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="637d6-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="637d6-106">설명</span><span class="sxs-lookup"><span data-stu-id="637d6-106">Remarks</span></span>  
 <span data-ttu-id="637d6-107">\<value> 태그를 사용하면 속성이 나타내는 값을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="637d6-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="637d6-108">Visual Studio .NET 개발 환경에서 코드 마법사를 통해 속성을 추가하면 새 속성에 대해 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 태그가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="637d6-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="637d6-109">그런 다음 \<value> 태그를 수동으로 추가하여 속성이 나타내는 값을 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="637d6-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="637d6-110">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="637d6-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="637d6-111">예</span><span class="sxs-lookup"><span data-stu-id="637d6-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="637d6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="637d6-112">See Also</span></span>  
 [<span data-ttu-id="637d6-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="637d6-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="637d6-114">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="637d6-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
