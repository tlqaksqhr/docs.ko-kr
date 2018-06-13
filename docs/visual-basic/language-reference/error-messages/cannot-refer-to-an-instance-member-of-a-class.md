---
title: 클래스의 명시적 인스턴스가 없는 공유 메서드 또는 공유 멤버 이니셜라이저에서는 클래스의 인스턴스 멤버를 참조할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: 368539ed24d9819c8d1ddbbb9e3e0dff21d27c32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590185"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="11253-102">클래스의 명시적 인스턴스가 없는 공유 메서드 또는 공유 멤버 이니셜라이저에서는 클래스의 인스턴스 멤버를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11253-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="11253-103">공유 프로시저 내에서 클래스의 공유 되지 않은 멤버를 참조 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="11253-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="11253-104">다음 예제에서는 이러한 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11253-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="11253-105">위의 예에서 대입문 `x = 10` 이 오류 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="11253-106">공유 프로시저 인스턴스 변수를 액세스 하려고 합니다. 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="11253-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="11253-107">변수 `x` 로 선언 되지 않은 인스턴스 멤버 이므로 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="11253-108">클래스의 각 인스턴스 `sample` 는 고유한 개별 변수 `x`합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="11253-109">특정 인스턴스에서 설정 하거나 변수의 값을 변경 하면 `x`, 값의 영향을 주지 않습니다 `x` 다른 인스턴스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11253-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="11253-110">그러나 프로시저 `setX` 은 `Shared` 클래스의 모든 인스턴스에서 `sample`합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="11253-111">즉, 대신 개별 인스턴스와 독립적으로 작동 하지만 클래스의 인스턴스와 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11253-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="11253-112">특정 인스턴스와 연결 되지 있기 때문에 `setX` 인스턴스 변수를 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11253-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="11253-113">경우에 작동 해야 `Shared` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="11253-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="11253-114">때 `setX` 설정 하거나, 새 값이 클래스의 모든 인스턴스에서 사용할 수 있는 공유 변수 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="11253-115">**오류 ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="11253-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="11253-116">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="11253-116">To correct this error</span></span>  
  
1.  <span data-ttu-id="11253-117">클래스의 모든 인스턴스 간에 공유 하거나 각 인스턴스에 대해 개별적 멤버 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2.  <span data-ttu-id="11253-118">모든 인스턴스 간에 공유 되는 멤버의 단일 복사본 추가 `Shared` 키워드 멤버 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="11253-119">유지 된 `Shared` 프로시저 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="11253-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3.  <span data-ttu-id="11253-120">각 인스턴스에 멤버의 개별 복사본을 원하는 경우 지정 하지 않으면 `Shared` 멤버 선언에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="11253-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="11253-121">제거는 `Shared` 프로시저 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="11253-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11253-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11253-122">See Also</span></span>  
 [<span data-ttu-id="11253-123">공유</span><span class="sxs-lookup"><span data-stu-id="11253-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
