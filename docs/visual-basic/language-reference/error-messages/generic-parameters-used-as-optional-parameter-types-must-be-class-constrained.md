---
title: 선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590041"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="5b8f1-102">선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="5b8f1-103">프로시저는 참조 형식으로 제한 되지 않은 형식 매개 변수를 사용 하는 선택적 매개 변수로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="5b8f1-104">항상 각 선택적 매개 변수에 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="5b8f1-105">선택적 값 이어야 합니다는 매개 변수는 참조 형식의 경우 `Nothing`, 참조 형식에 대 한 유효한 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="5b8f1-106">그러나 매개 변수는 값 형식의 경우 해당 형식이 Visual Basic에서 미리 정의 된 기본 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="5b8f1-107">사용자 정의 구조와 같은 복합 값 형식에 유효한 기본값이 없는 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="5b8f1-108">형식 매개 변수는 선택적 매개 변수를 사용 하 여 유효한 기본값이 없고 값 형식의 문제를 방지 하려면 참조 형식의 임을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="5b8f1-109">즉, 형식 매개 변수를 사용 하 여 제한 해야는 `Class` 키워드 또는 특정 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="5b8f1-110">**오류 ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="5b8f1-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b8f1-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5b8f1-111">To correct this error</span></span>  
  
-   <span data-ttu-id="5b8f1-112">형식 매개 변수는 참조 형식을 제한 하거나 선택적 매개 변수를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5b8f1-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b8f1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b8f1-113">See Also</span></span>  
 [<span data-ttu-id="5b8f1-114">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="5b8f1-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="5b8f1-115">형식 목록</span><span class="sxs-lookup"><span data-stu-id="5b8f1-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="5b8f1-116">Class 문</span><span class="sxs-lookup"><span data-stu-id="5b8f1-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="5b8f1-117">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b8f1-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="5b8f1-118">구조체</span><span class="sxs-lookup"><span data-stu-id="5b8f1-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="5b8f1-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="5b8f1-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
