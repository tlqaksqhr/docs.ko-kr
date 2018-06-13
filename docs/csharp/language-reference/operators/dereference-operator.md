---
title: -&gt; 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 037229b2081a43077cb4b5d02a8929b06ba9e077
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171982"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="8354c-102">-&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8354c-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="8354c-103">`->` 연산자는 포인터 역참조와 멤버 액세스를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="8354c-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8354c-104">설명</span><span class="sxs-lookup"><span data-stu-id="8354c-104">Remarks</span></span>  
 <span data-ttu-id="8354c-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8354c-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="8354c-106">여기서 `x`는 `T*` 형식의 포인터이고 `y`는 `T`의 멤버입니다. 이 식은 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8354c-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="8354c-107">`->` 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)로 표시된 코드에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8354c-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="8354c-108">`->` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8354c-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8354c-109">예</span><span class="sxs-lookup"><span data-stu-id="8354c-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8354c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8354c-110">See Also</span></span>  
 [<span data-ttu-id="8354c-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8354c-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8354c-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8354c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8354c-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8354c-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
