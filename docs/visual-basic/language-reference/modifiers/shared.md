---
title: Shared(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604551"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="f281b-102">Shared(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f281b-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="f281b-103">선언 된 프로그래밍 요소를 하나 이상의 클래스 또는 구조체의 특정 인스턴스가 아닌 클래스 또는 구조체도 연결 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f281b-104">설명</span><span class="sxs-lookup"><span data-stu-id="f281b-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="f281b-105">공유 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="f281b-105">When to Use Shared</span></span>  
 <span data-ttu-id="f281b-106">모든 인스턴스를 사용할 수 있도록 클래스 또는 구조체의 멤버를 공유 대신 *비공유*각 인스턴스는 자체 복사본을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="f281b-107">예를 들어 변수의 값이 전체 응용 프로그램에 적용 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="f281b-108">해당 변수를 선언 하는 경우 `Shared`모든 인스턴스에서 동일한 저장소 위치에 액세스 하 고 하나의 인스턴스만 해당 변수의 값을 변경 해도 모든 인스턴스에서 업데이트 된 값에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="f281b-109">공유 멤버의 액세스 수준을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="f281b-110">예를 들어, 클래스 멤버를 공유할 수 있습니다 및 private (내 에서만 액세스할 수는 클래스) 또는 비공유 및 공개 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="f281b-111">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f281b-112">규칙</span><span class="sxs-lookup"><span data-stu-id="f281b-112">Rules</span></span>  
  
-   <span data-ttu-id="f281b-113">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-113">**Declaration Context.**</span></span> <span data-ttu-id="f281b-114">`Shared`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="f281b-115">즉, 선언 컨텍스트는 `Shared` 요소는 클래스 또는 구조체 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="f281b-116">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-116">**Combined Modifiers.**</span></span> <span data-ttu-id="f281b-117">지정할 수 없습니다 `Shared` 와 함께 [재정의](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), 또는 [ 정적](../../../visual-basic/language-reference/modifiers/static.md) 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
-   <span data-ttu-id="f281b-118">**에 액세스합니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-118">**Accessing.**</span></span> <span data-ttu-id="f281b-119">공유 요소에 액세스 하면 해당 클래스 또는 구조체의 특정 인스턴스에의 변수 이름와 아닌에서 클래스나 구조체 이름으로 한정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="f281b-120">도 클래스 또는 해당 공유 멤버에 액세스 하는 구조체의 인스턴스를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="f281b-121">공유 프로시저를 호출 하는 다음 예제에서는 <xref:System.Double.IsNaN%2A> 의해 노출 되는 <xref:System.Double> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   <span data-ttu-id="f281b-122">**암시적 공유 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-122">**Implicit Sharing.**</span></span> <span data-ttu-id="f281b-123">사용할 수 없습니다는 `Shared` 한정자는 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md), 암시적으로 상수는 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="f281b-124">마찬가지로, 지정할 모듈 또는 인터페이스의 멤버를 선언할 수 없습니다 `Shared`, 없어도 암시적으로 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f281b-125">동작</span><span class="sxs-lookup"><span data-stu-id="f281b-125">Behavior</span></span>  
  
-   <span data-ttu-id="f281b-126">**저장소입니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-126">**Storage.**</span></span> <span data-ttu-id="f281b-127">만들 해당 클래스 또는 구조체의 인스턴스를 개수에 관계 없이 한 번만 공유 변수 또는 이벤트 메모리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="f281b-128">마찬가지로, 공유 프로시저 또는 속성이 하나의 지역 변수 집합을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
-   <span data-ttu-id="f281b-129">**인스턴스 변수를 통해 액세스 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="f281b-130">요소에 액세스 하는 공유의 해당 클래스 또는 구조체의 특정 인스턴스를 포함 하는 변수 이름으로 정규화 하 여는 것이 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="f281b-131">이 일반적으로 예상 대로 작동 하지만 컴파일러에서 경고 메시지를 생성 하 고 변수 대신 클래스 또는 구조체 이름 통해 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
-   <span data-ttu-id="f281b-132">**인스턴스 식을 통해에 액세스합니다.**</span><span class="sxs-lookup"><span data-stu-id="f281b-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="f281b-133">해당 클래스 또는 구조체의 인스턴스를 반환 하는 식을 통해 공유 요소를 액세스 하는 경우 컴파일러에서 식을 계산 하는 대신 클래스 또는 구조체 이름을 통해 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="f281b-134">다른 작업으로 인스턴스를 반환 하는 데 식을 사용 하는 경우 예기치 않은 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="f281b-135">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-135">The following example illustrates this.</span></span>  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="f281b-136">앞의 예제에서 컴파일러는 경고 메시지를 생성 코드 공유 변수에 액세스할 때마다 `total` 인스턴스를 통해 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="f281b-137">각 경우에는 클래스를 통해 직접 액세스 `shareTotal` 않습니다 인스턴스는 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="f281b-138">프로시저에 대 한 의도 한 호출의 경우 `returnClass`, 즉,에 대 한 호출도 생성 하지 않습니다 `returnClass`이므로 "이라는 함수 returnClass()"를 표시 합니다. 추가 동작이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="f281b-139">`Shared` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f281b-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f281b-140">Dim 문</span><span class="sxs-lookup"><span data-stu-id="f281b-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="f281b-141">Event 문</span><span class="sxs-lookup"><span data-stu-id="f281b-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="f281b-142">Function 문</span><span class="sxs-lookup"><span data-stu-id="f281b-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f281b-143">Operator 문</span><span class="sxs-lookup"><span data-stu-id="f281b-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="f281b-144">Property 문</span><span class="sxs-lookup"><span data-stu-id="f281b-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f281b-145">Sub 문</span><span class="sxs-lookup"><span data-stu-id="f281b-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f281b-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f281b-146">See Also</span></span>  
 [<span data-ttu-id="f281b-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="f281b-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="f281b-148">정적</span><span class="sxs-lookup"><span data-stu-id="f281b-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="f281b-149">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="f281b-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="f281b-150">절차</span><span class="sxs-lookup"><span data-stu-id="f281b-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="f281b-151">구조체</span><span class="sxs-lookup"><span data-stu-id="f281b-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="f281b-152">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="f281b-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
