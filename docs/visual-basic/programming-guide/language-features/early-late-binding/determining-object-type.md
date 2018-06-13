---
title: 개체 형식 확인(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a9852998abeae67b2a0e9dc3ffc85318ce5045da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648296"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="e8013-102">개체 형식 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8013-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="e8013-103">일반 개체 변수 (즉, 변수 선언으로 `Object`) 모든 클래스의 개체를에서 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="e8013-104">형식의 변수를 사용 하는 경우 `Object`, 개체의 클래스를 기반으로 하는 다른 작업을 수행 해야 할 수; 예를 들어 일부 개체 수 지원 하지 않습니다는 특정 속성 또는 메서드.</span><span class="sxs-lookup"><span data-stu-id="e8013-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="e8013-105">Visual Basic에서 개체 변수에 저장 됩니다 개체의 유형을 결정 하는 두 가지 방법을 제공:는 `TypeName` 함수 및 `TypeOf...Is` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="e8013-106">TypeName 및 TypeOf... 은</span><span class="sxs-lookup"><span data-stu-id="e8013-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="e8013-107">`TypeName` 함수는 문자열을 반환 하 고 다음 코드 조각에 나와 있는 것 처럼 개체의 클래스 이름을 저장 하거나 표시 해야 할 때이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 <span data-ttu-id="e8013-108">`TypeOf...Is` 연산자는 개체의 형식을 테스트 하기 위한 최상의 방법 사용 하 여 해당 하는 문자열 비교 보다 훨씬 빠릅니다 `TypeName`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="e8013-109">다음 코드 조각에서는 `TypeOf...Is` 내는 `If...Then...Else` 문:</span><span class="sxs-lookup"><span data-stu-id="e8013-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 <span data-ttu-id="e8013-110">주의할이 여기 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-110">A word of caution is due here.</span></span> <span data-ttu-id="e8013-111">`TypeOf...Is` 연산자는 반환 `True` 개체가 특정 유형의 또는 특정 형식에서 파생 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="e8013-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="e8013-112">Visual Basic을 사용한 수행 거의 모든 작업, 문자열 및 정수 같은 개체로 간주 일반적으로 일부 요소를 포함 하는 개체를 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="e8013-113">이러한 개체에서 파생 되 고 메서드를 상속 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="e8013-114">전달 될 때는 `Integer` 를 평가 하 고 `Object`, `TypeOf...Is` 연산자는 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="e8013-115">다음 예제에서는 보고 하는 매개 변수 `InParam` 둘는 `Object` 및 `Integer`:</span><span class="sxs-lookup"><span data-stu-id="e8013-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 <span data-ttu-id="e8013-116">다음 예제에서는 둘 다 사용 하 여 `TypeOf...Is` 및 `TypeName` 에서 전달 된 개체의 형식을 확인 하는 `Ctrl` 인수.</span><span class="sxs-lookup"><span data-stu-id="e8013-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="e8013-117">`TestObject` 프로시저 호출 `ShowType` 세 가지 다른 종류의 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="e8013-118">예제를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e8013-118">To run the example</span></span>  
  
1.  <span data-ttu-id="e8013-119">새 Windows 응용 프로그램 프로젝트를 만들고 추가 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Windows.Forms.CheckBox> 컨트롤 및 <xref:System.Windows.Forms.RadioButton> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="e8013-120">폼에 단추에서 호출 된 `TestObject` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="e8013-121">폼에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8013-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e8013-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8013-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [<span data-ttu-id="e8013-123">문자열 이름을 사용하여 속성 또는 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="e8013-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [<span data-ttu-id="e8013-124">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8013-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="e8013-125">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="e8013-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="e8013-126">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8013-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="e8013-127">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e8013-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
