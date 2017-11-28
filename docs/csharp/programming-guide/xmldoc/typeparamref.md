---
title: "&lt;typeparamref&gt;(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 296761f72d3d306c4f37632d7110e31b62c44734
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="13f19-102">&lt;typeparamref&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="13f19-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="13f19-103">구문</span><span class="sxs-lookup"><span data-stu-id="13f19-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13f19-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13f19-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="13f19-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="13f19-105">The name of the type parameter.</span></span> <span data-ttu-id="13f19-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="13f19-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13f19-107">설명</span><span class="sxs-lookup"><span data-stu-id="13f19-107">Remarks</span></span>  
 <span data-ttu-id="13f19-108">제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f19-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="13f19-109">이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13f19-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="13f19-110">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="13f19-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13f19-111">예제</span><span class="sxs-lookup"><span data-stu-id="13f19-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="13f19-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13f19-112">See Also</span></span>  
 [<span data-ttu-id="13f19-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="13f19-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="13f19-114">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="13f19-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
