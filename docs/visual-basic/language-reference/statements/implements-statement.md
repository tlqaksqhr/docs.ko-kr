---
title: Implements 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244742"
---
# <a name="implements-statement"></a><span data-ttu-id="6e145-102">Implements 문</span><span class="sxs-lookup"><span data-stu-id="6e145-102">Implements Statement</span></span>
<span data-ttu-id="6e145-103">인터페이스 또는 클래스에서 구현 해야 하는 인터페이스 멤버의 경우 또는 나타나는 구조 정의 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e145-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e145-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="6e145-105">요소</span><span class="sxs-lookup"><span data-stu-id="6e145-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="6e145-106">필수.</span><span class="sxs-lookup"><span data-stu-id="6e145-106">Required.</span></span> <span data-ttu-id="6e145-107">해당 속성, 프로시저 및 이벤트 클래스 또는 구조체에서 해당 멤버에 의해 구현 되어야 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="6e145-108">필수.</span><span class="sxs-lookup"><span data-stu-id="6e145-108">Required.</span></span> <span data-ttu-id="6e145-109">구현 되는 인터페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e145-110">설명</span><span class="sxs-lookup"><span data-stu-id="6e145-110">Remarks</span></span>  
 <span data-ttu-id="6e145-111">인터페이스는 컬렉션의 프로토타입 멤버 (속성, 프로시저 및 이벤트)를 나타내는 인터페이스를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="6e145-112">인터페이스 멤버;에 대 한 선언에만 포함 클래스와 구조체는 이러한 멤버를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="6e145-113">자세한 내용은 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e145-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="6e145-114">합니다 `Implements` 문 바로 뒤에 나와야 합니다 `Class` 또는 `Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="6e145-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="6e145-115">인터페이스를 구현 하는 경우 인터페이스에서 선언 된 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="6e145-116">모든 멤버를 생략 하면 구문 오류가 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="6e145-117">개별 멤버를 구현 하려면 지정 합니다 [구현](../../../visual-basic/language-reference/statements/implements-clause.md) 키워드 (분리 되는 `Implements` 문) 클래스 또는 구조체에서 멤버를 선언 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="6e145-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="6e145-118">자세한 내용은 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e145-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="6e145-119">클래스를 사용할 수 있습니다 [개인](../../../visual-basic/language-reference/modifiers/private.md) 속성 프로시저 하며 이러한 멤버의 구현을 인터페이스의 형식으로 선언 된 변수를 구현 하는 클래스의 인스턴스로 캐스팅 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e145-120">예</span><span class="sxs-lookup"><span data-stu-id="6e145-120">Example</span></span>  
 <span data-ttu-id="6e145-121">다음 예제에서는 사용 하는 방법의 `Implements` 인터페이스의 멤버를 구현 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="6e145-122">라는 인터페이스가 정의 `ICustomerInfo` 이벤트, 속성 및 프로시저를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="6e145-123">클래스 `customerInfo` 인터페이스에 정의 된 모든 멤버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="6e145-124">클래스 `customerInfo` 사용 하는 `Implements` 클래스의 모든 멤버를 구현 함을 나타내기 위해 별도 소스 코드 줄에서 문은 `ICustomerInfo` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="6e145-125">각 멤버는 클래스에서 사용 하 여는 `Implements` 키워드는 인터페이스 멤버를 구현 함을 나타내려면 멤버 선언의 일부로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e145-126">예</span><span class="sxs-lookup"><span data-stu-id="6e145-126">Example</span></span>  
 <span data-ttu-id="6e145-127">다음 두 절차 앞의 예제에서 구현 된 인터페이스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="6e145-128">구현을 테스트 하려면 다음이 절차 호출 프로젝트에 추가 된 `testImplements` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="6e145-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6e145-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e145-129">See Also</span></span>  
 [<span data-ttu-id="6e145-130">Implements</span><span class="sxs-lookup"><span data-stu-id="6e145-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="6e145-131">Interface 문</span><span class="sxs-lookup"><span data-stu-id="6e145-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="6e145-132">인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e145-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
