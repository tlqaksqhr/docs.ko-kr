---
title: "개체 형식 확인 (Visual Basic) | Microsoft 문서"
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
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
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
ms.openlocfilehash: fec7a275029dde469425b651d5b1220cb21ddbf6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="4496a-102">개체 형식 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4496a-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="4496a-103">일반 개체 변수 (즉, 변수 선언으로 `Object`) 모든 클래스의 개체를에서 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="4496a-104">형식의 변수를 사용 하는 경우 `Object`, 개체의 클래스를 기반으로 하는 다른 작업을 수행 해야 할 수 있습니다; 예를 들어 일부 개체 수 지원 하지 않습니다 특정 속성 또는 메서드.</span><span class="sxs-lookup"><span data-stu-id="4496a-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4496a-105">개체의 형식을 개체 변수에 저장 됩니다 결정 하는 두 가지 방법을 제공 합니다:는 `TypeName` 함수 및 `TypeOf...Is` 연산자.</span><span class="sxs-lookup"><span data-stu-id="4496a-105"> provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="4496a-106">TypeName 및 TypeOf... 은</span><span class="sxs-lookup"><span data-stu-id="4496a-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="4496a-107">`TypeName` 함수는 문자열을 반환 하 고 다음 코드 조각에서와 같이 개체의 클래스 이름을 저장 하거나 표시 해야 할 때 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="4496a-108">[!code-vb[VbVbalrOOP #&92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4496a-108">[!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span></span>  
  
 <span data-ttu-id="4496a-109">`TypeOf...Is` 연산자는 개체의 형식을 테스트 하기 위한 최상의 방법 사용 하 여 해당 하는 문자열 비교 보다 훨씬 빠릅니다 `TypeName`합니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-109">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="4496a-110">다음 코드 조각에서는 `TypeOf...Is` 내는 `If...Then...Else` 문:</span><span class="sxs-lookup"><span data-stu-id="4496a-110">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 <span data-ttu-id="4496a-111">[!code-vb[VbVbalrOOP #&93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4496a-111">[!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span></span>  
  
 <span data-ttu-id="4496a-112">주의할 여기 기한입니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-112">A word of caution is due here.</span></span> <span data-ttu-id="4496a-113">`TypeOf...Is` 연산자 반환 `True` 개체가 특정 형식 또는 특정 형식에서 파생 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="4496a-113">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="4496a-114">거의 모든 작업을 할 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 일반적으로 문자열이 나 정수와 같은 개체 라고 하는 일부 요소를 포함 하는 개체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-114">Almost everything you do with [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="4496a-115">이러한 개체에서 파생 되 고 <xref:System.Object>.</xref:System.Object> 메서드를 상속</span><span class="sxs-lookup"><span data-stu-id="4496a-115">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="4496a-116">전달 하는 경우는 `Integer` 를 평가 하 고 `Object`, `TypeOf...Is` 연산자 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-116">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="4496a-117">다음 예제에서는 보고 하는 매개 변수 `InParam` 둘는 `Object` 및 `Integer`:</span><span class="sxs-lookup"><span data-stu-id="4496a-117">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 <span data-ttu-id="4496a-118">[!code-vb[VbVbalrOOP #&94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4496a-118">[!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span></span>  
  
 <span data-ttu-id="4496a-119">둘 다 사용 하 여 다음 예제 `TypeOf...Is` 및 `TypeName` 에 전달 된 개체의 형식을 확인 하는 `Ctrl` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-119">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="4496a-120">`TestObject` 프로시저 호출 `ShowType` 세 개의 서로 다른 종류의 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-120">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="4496a-121">예제를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4496a-121">To run the example</span></span>  
  
1.  <span data-ttu-id="4496a-122">새 Windows 응용 프로그램 프로젝트를 만들고 추가 <xref:System.Windows.Forms.Button>제어는 <xref:System.Windows.Forms.CheckBox>컨트롤 및 <xref:System.Windows.Forms.RadioButton>컨트롤을 폼.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="4496a-122">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="4496a-123">폼에 단추에서 호출 된 `TestObject` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-123">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="4496a-124">폼에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4496a-124">Add the following code to your form:</span></span>  
  
     <span data-ttu-id="4496a-125">[!code-vb[VbVbalrOOP #&95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4496a-125">[!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4496a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4496a-126">See Also</span></span>  
 <span data-ttu-id="4496a-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A></span><span class="sxs-lookup"><span data-stu-id="4496a-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></span></span>   
<span data-ttu-id="4496a-128"> [속성 또는 문자열 이름을 사용 하 여 메서드 호출](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span><span class="sxs-lookup"><span data-stu-id="4496a-128"> [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span></span>  
<span data-ttu-id="4496a-129"> [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="4496a-129"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="4496a-130"> [다음과 같은 경우... 다음 중... Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4496a-130"> [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span></span>  
<span data-ttu-id="4496a-131"> [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="4496a-131"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="4496a-132"> [Integer 데이터 형식](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="4496a-132"> [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span></span>
