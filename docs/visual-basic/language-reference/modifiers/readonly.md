---
title: ReadOnly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599914"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="142a0-102">ReadOnly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="142a0-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="142a0-103">변수 또는 속성 읽을 수 있지만 기록 되지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="142a0-104">설명</span><span class="sxs-lookup"><span data-stu-id="142a0-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="142a0-105">규칙</span><span class="sxs-lookup"><span data-stu-id="142a0-105">Rules</span></span>  
  
-   <span data-ttu-id="142a0-106">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="142a0-106">**Declaration Context.**</span></span> <span data-ttu-id="142a0-107">`ReadOnly`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="142a0-108">즉, 선언 컨텍스트는 `ReadOnly` 요소 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="142a0-109">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="142a0-109">**Combined Modifiers.**</span></span> <span data-ttu-id="142a0-110">지정할 수 없으며 `ReadOnly` 와 함께 `Static` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="142a0-111">**값을 할당 합니다.**</span><span class="sxs-lookup"><span data-stu-id="142a0-111">**Assigning a Value.**</span></span> <span data-ttu-id="142a0-112">사용 하는 코드는 `ReadOnly` 속성의 값을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="142a0-113">하지만 기본 저장소에 액세스할 수 있는 코드를 할당 하거나 언제 든 지 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="142a0-114">값을 할당할 수는 `ReadOnly` 변수 선언 또는 정의 된 구조체 또는 클래스의 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="142a0-115">읽기 전용 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="142a0-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="142a0-116">경우에 사용할 수 없습니다는 [Const 문을](../../../visual-basic/language-reference/statements/const-statement.md) 선언 하 고 상수 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="142a0-117">예를 들어는 `Const` 문을 할당 하려면 원하는 데이터 형식을 허용 되지 않거나를 상수 식으로 컴파일 타임에 값을 계산 하는 일을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="142a0-118">하지 컴파일 타임에 값을도 알고 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="142a0-119">이러한 경우에 사용할 수 있습니다는 `ReadOnly` 상수 값을 보유할 변수로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="142a0-120">변수 자체는 경우에 해당 멤버를 변경할 수는 변수의 데이터 형식을 배열 또는 클래스 인스턴스를 같은 참조 형식이 면 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="142a0-121">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="142a0-122">를 초기화할 때 배열을 가리키는 `characterArray()` "x", "y" 및 "z"입니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="142a0-123">때문에 변수 `characterArray` 은 `ReadOnly`, 초기화 된 후; 되 해당 값을 변경할 수 없습니다, 새 배열을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="142a0-124">그러나 하나 이상의 배열 멤버의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="142a0-125">프로시저를 호출한 다음 `changeArrayElement`를 가리키는 배열 `characterArray()` "x", "M" 및 "z"입니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="142a0-126">이 프로시저 매개 변수를 선언 하는 비슷한 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), 하면 프로시저가 호출 인수 자체를 변경할 수는 있지만 해당 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="142a0-127">예제</span><span class="sxs-lookup"><span data-stu-id="142a0-127">Example</span></span>  
 <span data-ttu-id="142a0-128">다음 예제에서는 정의 `ReadOnly` 직원이 고용 된 날짜에 대 한 속성.</span><span class="sxs-lookup"><span data-stu-id="142a0-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="142a0-129">속성 값을 내부적으로 클래스 저장소는 `Private` 클래스의 내부 변수와 유일한 코드는 해당 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="142a0-130">그러나 속성은 `Public`, 클래스에 액세스할 수 있는 모든 코드는 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 <span data-ttu-id="142a0-131">`ReadOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="142a0-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="142a0-132">Dim 문</span><span class="sxs-lookup"><span data-stu-id="142a0-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="142a0-133">Property 문</span><span class="sxs-lookup"><span data-stu-id="142a0-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="142a0-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="142a0-134">See Also</span></span>  
 [<span data-ttu-id="142a0-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="142a0-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="142a0-136">키워드</span><span class="sxs-lookup"><span data-stu-id="142a0-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
