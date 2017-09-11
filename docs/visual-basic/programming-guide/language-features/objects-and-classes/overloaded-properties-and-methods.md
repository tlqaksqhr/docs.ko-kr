---
title: "속성 및 메서드 (Visual Basic)를 오버 로드 된 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0b0040f78fd8e091027e32efae3a0f26c2a08622
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="8b1f9-102">오버로드된 속성 및 메서드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b1f9-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="8b1f9-103">오버 로딩은 둘 이상의 프로시저, 인스턴스 생성자 또는 속성 이름은 같지만 다른 형식의 인수를 사용 하 여 클래스에 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="8b1f9-104">오버 로드 사용</span><span class="sxs-lookup"><span data-stu-id="8b1f9-104">Overloading Usage</span></span>  
 <span data-ttu-id="8b1f9-105">오버 로드 개체 모델에 다른 데이터 형식에서 작동 하는 프로시저에 대 한 동일한 이름을 사용 하도록 요구할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="8b1f9-106">예를 들어, 여러 다른 데이터 형식을 표시할 수 있는 클래스를 가지기 `Display` 프로시저를 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 <span data-ttu-id="8b1f9-107">[!code-vb[VbVbalrOOP #&64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b1f9-107">[!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="8b1f9-108">오버 로드 하지 않고 해야 각 프로시저에 대 한 고유 이름을 만들기 위해 다음과 같이 동일한 작업을 그럴 경우에:</span><span class="sxs-lookup"><span data-stu-id="8b1f9-108">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 <span data-ttu-id="8b1f9-109">[!code-vb[VbVbalrOOP #&65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b1f9-109">[!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="8b1f9-110">오버 로드 하면 다양 한 데이터 형식 사용할 수 있는 제공 하기 때문에 속성이 나 메서드를 사용 하 여 쉽게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-110">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="8b1f9-111">예를 들어, 오버 로드 된 `Display` 다음 줄의 코드를 사용 하 여 호출할 수 이전에 앞에서 설명한 메서드:</span><span class="sxs-lookup"><span data-stu-id="8b1f9-111">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 <span data-ttu-id="8b1f9-112">[!code-vb[VbVbalrOOP #&66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b1f9-112">[!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="8b1f9-113">런타임 시 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 올바른 프로시저 매개 변수의 데이터 형식에 따라 호출을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-113">At run time, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="8b1f9-114">오버 로드 규칙</span><span class="sxs-lookup"><span data-stu-id="8b1f9-114">Overloading Rules</span></span>  
 <span data-ttu-id="8b1f9-115">두 개 이상의 속성 또는 동일한 이름 가진 메서드를 추가 하 여 클래스에 대 한 오버 로드 된 멤버를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-115">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="8b1f9-116">파생된 멤버 오버 로드를 제외 하 고 각 멤버는 다른 매개 변수 목록을 있어야 하 고 속성이 나 프로시저를 오버 로드할 때 다음 항목을 별도 기능으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-116">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="8b1f9-117">한정자와 같은 `ByVal` 또는 `ByRef`, 멤버 또는 멤버의 매개 변수를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-117">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="8b1f9-118">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="8b1f9-118">Names of parameters</span></span>  
  
-   <span data-ttu-id="8b1f9-119">프로시저의 반환 형식</span><span class="sxs-lookup"><span data-stu-id="8b1f9-119">Return types of procedures</span></span>  
  
 <span data-ttu-id="8b1f9-120">`Overloads` 키워드는 오버 로드 하는 경우 선택 사항 이지만 멤버를 사용 하는 경우 오버 로드는 `Overloads` 키워드를 다음 같은 이름 가진 다른 모든 오버 로드 된 멤버 해야이 키워드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-120">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="8b1f9-121">파생된 클래스에서 상속된 된 멤버를 동일한 매개 변수 및 매개 변수 형식, 즉, 멤버를 오버 로드할 수 있습니다 *이름 및 서명을 숨길*합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-121">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="8b1f9-122">하는 경우는 `Overloads` 이름 및 시그니처로 숨김에 멤버의 경우 파생된 클래스의 구현 대신 사용 됩니다 기본 클래스에서 구현 하 고 해당 멤버에 대 한 다른 모든 오버 로드는 파생된 클래스의 인스턴스를 사용할 수 있습니다 때 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-122">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="8b1f9-123">하는 경우는 `Overloads` 키워드를 생략 하면 동일한 매개 변수 및 매개 변수 형식, 멤버와 상속된 된 멤버를 오버 로드할 때 다음는 오버 로딩 이라고 *이름 숨김은*합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-123">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="8b1f9-124">상속 된 멤버의 구현을 대체 이름 숨김은 하 고 다른 모든 오버 로드는 파생된 클래스 및 관련 계승자의 인스턴스를 사용할 수 없는입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-124">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="8b1f9-125">`Overloads` 및 `Shadows` 한정자 동일한 속성 또는 메서드를 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-125">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8b1f9-126">예제</span><span class="sxs-lookup"><span data-stu-id="8b1f9-126">Example</span></span>  
 <span data-ttu-id="8b1f9-127">다음 예제에서는 오버 로드 된 메서드 중 하나를 허용 하는 한 `String` 또는 `Decimal` 달러 금액 및 반환 판매세가 포함 된 문자열 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-127">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="8b1f9-128">이 예제를 사용 하려면이 오버 로드 된 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8b1f9-128">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="8b1f9-129">라는 클래스를 추가 하 고 새 프로젝트를 열고 `TaxClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-129">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="8b1f9-130">`TaxClass` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-130">Add the following code to the `TaxClass` class.</span></span>  
  
     <span data-ttu-id="8b1f9-131">[!code-vb[VbVbalrOOP #&67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b1f9-131">[!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span></span>  
  
3.  <span data-ttu-id="8b1f9-132">다음 절차를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-132">Add the following procedure to your form.</span></span>  
  
     <span data-ttu-id="8b1f9-133">[!code-vb[VbVbalrOOP #&68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b1f9-133">[!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span></span>  
  
4.  <span data-ttu-id="8b1f9-134">폼 및 호출에 단추 추가 `ShowTax` 에서 프로시저는 `Button1_Click` 단추의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-134">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="8b1f9-135">프로젝트를 실행 하 고 테스트는 오버 로드 된 폼에서 단추를 클릭 `ShowTax` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-135">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="8b1f9-136">런타임 시 컴파일러는 사용 중인 매개 변수와 일치 하는 적절 한 오버 로드 된 함수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-136">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="8b1f9-137">단추를 클릭할 경우의 오버 로드 된 메서드는 먼저는 `Price` 매개 변수를 문자열 및 메시지를 "가격은 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-137">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="8b1f9-138">세금은 $5.12"표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-138">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="8b1f9-139">`TaxAmount`호출 되는 `Decimal` 값, 두 번째 시간 및 메시지, "가격을&10; 진수로.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-139">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="8b1f9-140">세금은 $5.12"표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b1f9-140">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1f9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b1f9-141">See Also</span></span>  
 <span data-ttu-id="8b1f9-142">[개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-142">[Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="8b1f9-143"> [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-143"> [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span></span>  
<span data-ttu-id="8b1f9-144"> [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-144"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="8b1f9-145"> [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-145"> [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span></span>  
<span data-ttu-id="8b1f9-146"> [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-146"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="8b1f9-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span></span>  
<span data-ttu-id="8b1f9-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span></span>  
<span data-ttu-id="8b1f9-149"> [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="8b1f9-149"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="8b1f9-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span><span class="sxs-lookup"><span data-stu-id="8b1f9-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span></span>
