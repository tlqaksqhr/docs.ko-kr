---
title: '방법: 변수의 사용 가능성 제어(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 27ee5d3405ea24c0754cffa85e9b89b2ac561e42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652170"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="15476-102">방법: 변수의 사용 가능성 제어(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15476-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="15476-103">지정 하 여 변수의 사용 가능성 제어 해당 *액세스 수준*합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="15476-104">액세스 수준 변수에 쓰거나 읽을 수 있는 코드를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="15476-105">*멤버 변수* (프로시저 외부 및 모듈 수준에서 정의 됨) 기본적으로 공용 액세스를 확인 하는 모든 코드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="15476-106">액세스 한정자를 지정 하 여이 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="15476-107">*지역 변수* (프로시저 내에 정의 된)가 프로시저 내의 코드만 액세스할 수 있지만 공용 액세스 명목상으로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="15476-108">지역 변수 형식의 액세스 수준을 변경할 수 없습니다 하지만 포함 된 프로시저의 액세스 수준을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="15476-109">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="15476-110">개인 및 공용 액세스</span><span class="sxs-lookup"><span data-stu-id="15476-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="15476-111">변수를 해당 모듈, 클래스 또는 구조체 내 에서만 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="15476-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1.  <span data-ttu-id="15476-112">위치는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 프로시저 외부에 모듈, 클래스 또는 구조체 내에서 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="15476-113">포함는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="15476-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="15476-114">읽거나에서 아니라 하지만 모듈, 클래스 또는 구조체 내에서 변수를 쓸 수 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="15476-115">변수를 볼 수 있는 모든 코드에서 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="15476-115">To make a variable accessible from any code that can see it</span></span>  
  
1.  <span data-ttu-id="15476-116">멤버 변수를 배치에서 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="15476-117">포함는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="15476-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="15476-118">읽기 또는 어셈블리와 함께 상호 작용 하는 모든 코드에서 변수에 쓰기 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="15476-119">-또는-</span><span class="sxs-lookup"><span data-stu-id="15476-119">-or-</span></span>  
  
1.  <span data-ttu-id="15476-120">지역 변수를 배치에서 `Dim` 프로시저 내의 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2.  <span data-ttu-id="15476-121">포함 되지 않습니다는 `Public` 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="15476-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="15476-122">읽거나에서 변수는 프로시저에서 아무 곳 이나 하지만에서 아니라에 쓸 수 밖에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="15476-123">보호 및 Friend 액세스</span><span class="sxs-lookup"><span data-stu-id="15476-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="15476-124">변수는 해당 클래스 및 모든 파생된 클래스 또는 어셈블리의 액세스 수준을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="15476-125">파생된 클래스에서 또는 동일한 어셈블리의 다른 위치에 코드에서 액세스할 수 있는 이러한 제한의 합집합을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="15476-126">결합 하 여이 합집합을 지정 된 `Protected` 및 `Friend` 동일한 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="15476-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="15476-127">변수는 해당 클래스와 모든 파생된 클래스 내 에서만 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="15476-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1.  <span data-ttu-id="15476-128">위치는 `Dim` 프로시저 외부 클래스 내에서 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="15476-129">포함는 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="15476-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="15476-130">읽거나,에서 파생 된 클래스 내에서 뿐 아니라 해당 클래스에서 변수를 쓸 수 파생 체인의 모든 클래스 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="15476-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="15476-131">변수를 동일한 어셈블리 내 에서만 액세스할 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="15476-131">To make a variable accessible only from within the same assembly</span></span>  
  
1.  <span data-ttu-id="15476-132">위치는 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="15476-133">포함는 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="15476-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="15476-134">읽거나에서 아니라 있지만 동일한 어셈블리에 있는 모든 코드에서 뿐만 아니라 모듈, 클래스 또는 구조체 내에서 변수를 쓸 수 어셈블리 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15476-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15476-135">예제</span><span class="sxs-lookup"><span data-stu-id="15476-135">Example</span></span>  
 <span data-ttu-id="15476-136">다음 예제에서는 사용한 변수 선언을 `Public`, `Protected`, `Friend`, `Protected Friend`, 및 `Private` 액세스 수준을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="15476-137">경우는 `Dim` 문에서 액세스 수준을 포함할 필요가 없습니다는 `Dim` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="15476-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="15476-138">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="15476-138">.NET Framework Security</span></span>  
 <span data-ttu-id="15476-139">더 제한적인 변수를 액세스 수준에 악성 코드가 부적절 하 게 가능성이 줄어듭니다 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15476-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15476-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15476-140">See Also</span></span>  
 [<span data-ttu-id="15476-141">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="15476-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="15476-142">Dim 문</span><span class="sxs-lookup"><span data-stu-id="15476-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="15476-143">공용</span><span class="sxs-lookup"><span data-stu-id="15476-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="15476-144">보호됨</span><span class="sxs-lookup"><span data-stu-id="15476-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="15476-145">Friend</span><span class="sxs-lookup"><span data-stu-id="15476-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="15476-146">전용</span><span class="sxs-lookup"><span data-stu-id="15476-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
