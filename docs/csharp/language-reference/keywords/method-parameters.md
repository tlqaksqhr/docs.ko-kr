---
title: "메서드 매개 변수(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 8
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
ms.openlocfilehash: 4ba57e1a9e904befe11ff41796c987bd8f93b081
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="7687e-102">메서드 매개 변수(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7687e-102">Method Parameters (C# Reference)</span></span>
<span data-ttu-id="7687e-103">매개 변수가 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out.md) 없이 메서드에 대해 선언된 경우 매개 변수에 값이 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7687e-103">If a parameter is declared for a method without [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md), the parameter can have a value associated with it.</span></span> <span data-ttu-id="7687e-104">메서드에서 해당 값을 변경할 수 있지만, 제어가 호출하는 프로시저로 다시 전달되면 변경된 값이 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7687e-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="7687e-105">메서드 매개 변수 키워드를 사용하여 이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7687e-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="7687e-106">이 섹션에서는 메서드 매개 변수를 선언할 때 사용할 수 있는 키워드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7687e-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="7687e-107">params</span><span class="sxs-lookup"><span data-stu-id="7687e-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="7687e-108">ref</span><span class="sxs-lookup"><span data-stu-id="7687e-108">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="7687e-109">out</span><span class="sxs-lookup"><span data-stu-id="7687e-109">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
  
## <a name="see-also"></a><span data-ttu-id="7687e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7687e-110">See Also</span></span>  
 <span data-ttu-id="7687e-111">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7687e-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7687e-112">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7687e-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7687e-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="7687e-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

