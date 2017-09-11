---
title: "개체 변수 값 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: 5f42706a79212ae523b08ee336fdcacb3f761af6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="3d286-102">개체 변수 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d286-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="3d286-103">변수는 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 모든 형식의 데이터를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="3d286-104">에 저장 되는 값은 `Object` 변수는 특정 위치에 보관 메모리 변수 자체가 데이터에 대 한 포인터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="3d286-105">개체 분류자 함수</span><span class="sxs-lookup"><span data-stu-id="3d286-105">Object Classifier Functions</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="3d286-106">에 대 한 정보를 반환 하는 함수를 제공 하는 `Object` 변수가 참조 하는 다음 표에 나와 있는 것 처럼입니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-106"> supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d286-107">함수</span><span class="sxs-lookup"><span data-stu-id="3d286-107">Function</span></span>|<span data-ttu-id="3d286-108">개체 변수가 참조 하는 경우 True를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<span data-ttu-id="3d286-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></span></span>|<span data-ttu-id="3d286-110">단일 값이 아닌 값의 배열</span><span class="sxs-lookup"><span data-stu-id="3d286-110">An array of values, rather than a single value</span></span>|  
|<span data-ttu-id="3d286-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></span></span>|<span data-ttu-id="3d286-112">A [Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 값 또는 날짜 및 시간 값으로 해석 될 수 있는 문자열</span><span class="sxs-lookup"><span data-stu-id="3d286-112">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<span data-ttu-id="3d286-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span></span>|<span data-ttu-id="3d286-114">형식 <xref:System.DBNull>누락 되었거나 존재 하지 않는 데이터를 나타내는</xref:System.DBNull> 개체</span><span class="sxs-lookup"><span data-stu-id="3d286-114">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<span data-ttu-id="3d286-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></span></span>|<span data-ttu-id="3d286-116">파생 되는 예외 개체<xref:System.Exception></xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="3d286-116">An exception object, which derives from <xref:System.Exception></span></span>|  
|<span data-ttu-id="3d286-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></span></span>|<span data-ttu-id="3d286-118">[아무 것도](../../../../visual-basic/language-reference/nothing.md), 개체가 변수에 현재 할당 되어, 즉</span><span class="sxs-lookup"><span data-stu-id="3d286-118">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<span data-ttu-id="3d286-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span></span>|<span data-ttu-id="3d286-120">숫자 또는 문자열을 숫자로 해석 될 수 있는</span><span class="sxs-lookup"><span data-stu-id="3d286-120">A number, or a string that can be interpreted as a number</span></span>|  
|<span data-ttu-id="3d286-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="3d286-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></span></span>|<span data-ttu-id="3d286-122">참조 형식 (예: 문자열, 배열, 대리자 또는 클래스 형식)</span><span class="sxs-lookup"><span data-stu-id="3d286-122">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="3d286-123">작업 또는 프로시저에 잘못 된 값을 제출 하지 않으려면 이러한 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-123">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="3d286-124">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="3d286-124">TypeOf Operator</span></span>  
 <span data-ttu-id="3d286-125">사용할 수도 있습니다는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 개체 변수는 특정 데이터 형식으로 현재 참조 하는지 여부를 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="3d286-125">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="3d286-126">The `TypeOf`... `Is` 식이 `True` 피연산자의 런타임 형식에서 파생 되거나 지정 된 형식을 구현 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="3d286-126">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="3d286-127">다음 예제에서는 `TypeOf` 값 및 참조 형식을 참조 하는 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-127">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="3d286-128">앞의 예제에는 다음 줄을 씁니다는 **디버그** 창:</span><span class="sxs-lookup"><span data-stu-id="3d286-128">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="3d286-129">개체 변수 `num` 형식의 데이터를 가리키는 `Integer`, 및 `frm` <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form> 클래스의 개체 참조</span><span class="sxs-lookup"><span data-stu-id="3d286-129">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="3d286-130">개체 배열</span><span class="sxs-lookup"><span data-stu-id="3d286-130">Object Arrays</span></span>  
 <span data-ttu-id="3d286-131">선언 하 고 배열을 사용 하 여 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-131">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="3d286-132">다양 한 데이터 형식 및 개체 클래스를 처리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-132">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="3d286-133">배열의 모든 요소를 동일한 선언 된 데이터 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-133">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="3d286-134">이 데이터 형식으로 선언 `Object` 클래스 배열에 다른 데이터 형식과 함께 인스턴스 및 개체를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d286-134">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d286-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d286-135">See Also</span></span>  
 <span data-ttu-id="3d286-136">[개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-136">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="3d286-137"> [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-137"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="3d286-138"> [개체 변수 대입](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-138"> [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span></span>  
<span data-ttu-id="3d286-139"> [방법: 개체의 현재 인스턴스 참조](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-139"> [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="3d286-140"> [방법: 개체 변수가 참조 하는 형식 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-140"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="3d286-141"> [방법: 두 개체가 관련이 있는지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-141"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="3d286-142"> [방법: 두 개체가 동일한 지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span><span class="sxs-lookup"><span data-stu-id="3d286-142"> [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span></span>  
<span data-ttu-id="3d286-143"> [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="3d286-143"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
