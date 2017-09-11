---
title: "-&gt; 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ->_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
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
ms.openlocfilehash: f42135e43bdfc58ee64fd3465074b3f8791f8ada
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="23e3f-102">-&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="23e3f-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="23e3f-103">`->` 연산자는 포인터 역참조와 멤버 액세스를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23e3f-104">설명</span><span class="sxs-lookup"><span data-stu-id="23e3f-104">Remarks</span></span>  
 <span data-ttu-id="23e3f-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-105">An expression of the form,</span></span>  
  
```  
x->y  
```  
  
 <span data-ttu-id="23e3f-106">여기서 `x`는 `T*` 형식의 포인터이고 `y`는 `T`의 멤버입니다. 이 식은 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```  
(*x).y  
```  
  
 <span data-ttu-id="23e3f-107">`->` 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)로 표시된 코드에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="23e3f-108">`->` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23e3f-109">예제</span><span class="sxs-lookup"><span data-stu-id="23e3f-109">Example</span></span>  
 <span data-ttu-id="23e3f-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="23e3f-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e3f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23e3f-111">See Also</span></span>  
 <span data-ttu-id="23e3f-112">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="23e3f-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="23e3f-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="23e3f-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="23e3f-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="23e3f-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

