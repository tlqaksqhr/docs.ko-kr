---
title: "&lt;typeparamref&gt;(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparamref
dev_langs:
- CSharp
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce2aba7a14047066decf85675233a48a08bfd605
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="8db95-102">&lt;typeparamref&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8db95-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8db95-103">구문</span><span class="sxs-lookup"><span data-stu-id="8db95-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8db95-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8db95-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8db95-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8db95-105">The name of the type parameter.</span></span> <span data-ttu-id="8db95-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="8db95-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8db95-107">설명</span><span class="sxs-lookup"><span data-stu-id="8db95-107">Remarks</span></span>  
 <span data-ttu-id="8db95-108">제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8db95-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="8db95-109">이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8db95-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="8db95-110">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8db95-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8db95-111">예제</span><span class="sxs-lookup"><span data-stu-id="8db95-111">Example</span></span>  
 <span data-ttu-id="8db95-112">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8db95-112">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db95-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8db95-113">See Also</span></span>  
 <span data-ttu-id="8db95-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8db95-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8db95-115">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="8db95-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

