---
title: "&lt;typeparam&gt;(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
dev_langs:
- CSharp
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
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
ms.openlocfilehash: 8bb1d13976cf2cc9df4f573702168c6abdfff3d5
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="9d1e0-102">&lt;typeparam&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9d1e0-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="9d1e0-103">구문</span><span class="sxs-lookup"><span data-stu-id="9d1e0-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d1e0-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d1e0-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9d1e0-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-105">The name of the type parameter.</span></span> <span data-ttu-id="9d1e0-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="9d1e0-107">형식 매개 변수에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d1e0-108">설명</span><span class="sxs-lookup"><span data-stu-id="9d1e0-108">Remarks</span></span>  
 <span data-ttu-id="9d1e0-109">`<typeparam>` 태그는 제네릭 형식 또는 메서드 선언의 주석에서 형식 매개 변수를 설명하는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="9d1e0-110">제네릭 형식 또는 메서드의 각 형식 매개 변수에 대한 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="9d1e0-111">자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="9d1e0-112">`<typeparam>` 태그에 대한 텍스트는 IntelliSense와 [개체 브라우저 창](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)의 코드 주석 웹 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="9d1e0-113">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1e0-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d1e0-114">예제</span><span class="sxs-lookup"><span data-stu-id="9d1e0-114">Example</span></span>  
 <span data-ttu-id="9d1e0-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d1e0-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d1e0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d1e0-116">See Also</span></span>  
 <span data-ttu-id="9d1e0-117">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d1e0-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9d1e0-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d1e0-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9d1e0-119">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="9d1e0-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

