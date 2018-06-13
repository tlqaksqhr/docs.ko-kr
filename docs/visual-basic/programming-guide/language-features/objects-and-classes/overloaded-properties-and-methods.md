---
title: 오버 로드 된 속성 및 메서드 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652196"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="535bb-102">오버 로드 된 속성 및 메서드 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="535bb-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="535bb-103">오버 로드은 둘 이상의 인스턴스 생성자의에서 프로시저 또는 속성 이름은 같지만 서로 다른 인수 형식을 사용 하는 클래스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="535bb-104">오버 로드 사용</span><span class="sxs-lookup"><span data-stu-id="535bb-104">Overloading usage</span></span>

 <span data-ttu-id="535bb-105">오버 로드 개체 모델이 다른 데이터 형식에서 작동 하는 프로시저에 대 한 동일한 이름을 사용 하도록 요구할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="535bb-106">예를 들어 여러 다른 데이터 형식을 표시할 수 있는 클래스를 가지기 `Display` 는 다음과 같은 프로시저:</span><span class="sxs-lookup"><span data-stu-id="535bb-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 <span data-ttu-id="535bb-107">하지 않으면 오버 로드 해야 각 프로시저에 대 한 고유 이름을 만들려면 다음 예와 같이 동일한 작업을 수행 하는 경우에:</span><span class="sxs-lookup"><span data-stu-id="535bb-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 <span data-ttu-id="535bb-108">오버 로드 하면 보다 쉽게 사용할 수 있는 데이터 형식의 선택 항목을 제공 하기 때문에 속성이 나 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="535bb-109">예를 들어 오버 로드 된 `Display` 다음 줄의 코드를 사용 하 여 호출할 수 이전에 앞에서 설명한 메서드:</span><span class="sxs-lookup"><span data-stu-id="535bb-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 <span data-ttu-id="535bb-110">Visual Basic 런타임 시 지정한 매개 변수의 데이터 형식을 기반으로 올바른 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="535bb-111">규칙 오버 로드</span><span class="sxs-lookup"><span data-stu-id="535bb-111">Overloading rules</span></span>

 <span data-ttu-id="535bb-112">둘 이상의 속성이 나 같은 이름의 메서드를 추가 하 여 클래스에 대 한 오버 로드 된 멤버를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="535bb-113">오버 로드 된 파생된 멤버를 제외 하 고 각 멤버는 다른 매개 변수 목록을 있어야 하 고 속성 또는 프로시저를 오버 로드할 때 다음 항목을 별도 기능으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="535bb-114">한정자를 같은 `ByVal` 또는 `ByRef`, 멤버 또는 멤버의 매개 변수를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="535bb-115">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="535bb-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="535bb-116">프로시저의 반환 형식</span><span class="sxs-lookup"><span data-stu-id="535bb-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="535bb-117">`Overloads` 키워드는 오버 로드 하는 경우 선택 사항 이지만 구성원 사용 하 여 오버 로드 된 있는 경우는 `Overloads` 키워드를 다음 동일한 이름 가진 다른 모든 오버 로드 된 멤버 해야이 키워드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="535bb-118">파생된 클래스에서 상속된 된 멤버를 동일한 매개 변수 및 매개 변수 형식, 즉, 멤버를 오버 로드할 수 있습니다 *이름 및 서명을 갖는*합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="535bb-119">경우는 `Overloads` 이름 및 서명을 갖는, 멤버의 파생된 클래스의 구현 대신 사용할 기본 클래스에서 구현 하 고 해당 멤버에 대 한 다른 모든 오버 로드의 인스턴스를 사용할 수 있습니다 때 키워드가 사용 되는 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="535bb-120">경우는 `Overloads` 동일한 매개 변수 및 매개 변수 형식, 멤버와 상속된 된 멤버를 오버 로드할 때 키워드를 생략 한 후 호출 되는 오버 로딩 *이름 숨김은*합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="535bb-121">멤버의 상속 된 구현을 대체 이름 숨김은 하 고 다른 모든 오버 로드와 관련 계승자 파생된 클래스의 인스턴스를 사용할 수 없는입니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="535bb-122">`Overloads` 및 `Shadows` 한정자 동일한 속성 또는 메서드를 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="535bb-123">예제</span><span class="sxs-lookup"><span data-stu-id="535bb-123">Example</span></span>

 <span data-ttu-id="535bb-124">다음 예제에서는 중 하나를 허용 하는 오버 로드 된 메서드는 `String` 또는 `Decimal` 달러 금액 및 반환 세율이 포함 하는 문자열 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="535bb-125">오버 로드 된 메서드를 만들려면이 예제를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="535bb-125">To use this example to create an overloaded method</span></span>
  
1.  <span data-ttu-id="535bb-126">새 프로젝트를 열고 라는 클래스를 추가 `TaxClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="535bb-127">`TaxClass` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  <span data-ttu-id="535bb-128">다음 절차를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  <span data-ttu-id="535bb-129">단추를 폼과 호출 추가 `ShowTax` 에서 프로시저는 `Button1_Click` 단추의 이벤트가 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="535bb-130">프로젝트를 실행 하 고 오버 로드 된 테스트 하려면 폼에서 단추 클릭 `ShowTax` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="535bb-131">컴파일러는 실행 시 사용 되는 매개 변수와 일치 하는 적절 한 오버 로드 된 함수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="535bb-132">오버 로드 된 메서드를 먼저 호출한 단추를 클릭할 때 한 `Price` 문자열이 고 "가격은 문자열입니다 메시지를 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="535bb-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="535bb-133">세금은 $5.12"표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="535bb-134">`TaxAmount` 로 호출 되는 `Decimal` 값, 두 번째 시간 및 메시지, "가격을 10 진수로.</span><span class="sxs-lookup"><span data-stu-id="535bb-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="535bb-135">세금은 $5.12"표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="535bb-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535bb-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="535bb-136">See also</span></span>

 [<span data-ttu-id="535bb-137">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="535bb-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="535bb-138">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="535bb-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="535bb-139">Sub 문</span><span class="sxs-lookup"><span data-stu-id="535bb-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="535bb-140">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="535bb-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="535bb-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="535bb-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="535bb-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="535bb-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="535bb-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="535bb-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="535bb-144">오버로드</span><span class="sxs-lookup"><span data-stu-id="535bb-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="535bb-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="535bb-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
