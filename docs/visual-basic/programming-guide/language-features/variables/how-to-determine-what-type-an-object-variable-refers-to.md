---
title: "방법: 개체 변수가 참조하는 형식 확인(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5dd6785ecd48be3f0455de63b9e3f13a485ddbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="9b4d1-102">방법: 개체 변수가 참조하는 형식 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b4d1-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="9b4d1-103">개체 변수는 다른 위치에 저장 된 데이터에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="9b4d1-104">런타임 동안 해당 데이터의 형식은 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-104">The type of that data can change during run time.</span></span> <span data-ttu-id="9b4d1-105">언제 든 지 사용할 수 있습니다는 <xref:System.Type.GetTypeCode%2A> 현재 런타임 형식을 결정 하는 메서드 또는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 런타임 형식이 현재 했는지 확인 하 여 지정 된 형식의 호환 되는지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="9b4d1-106">참조 형식을 결정 하려면 정확한 개체 변수에 현재</span><span class="sxs-lookup"><span data-stu-id="9b4d1-106">To determine the exact type an object variable currently refers to</span></span>  
  
1.  <span data-ttu-id="9b4d1-107">개체 변수를 호출 하는 <xref:System.Object.GetType%2A> 를 검색할 메서드는 <xref:System.Type?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <span data-ttu-id="9b4d1-108">에 <xref:System.Type?displayProperty=nameWithType> 클래스를 공유 하는 메서드를 호출 <xref:System.Type.GetTypeCode%2A> 검색 하는 <xref:System.TypeCode> 개체의 형식에 대 한 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="9b4d1-109">테스트할 수 있습니다는 <xref:System.TypeCode> 같은 관심 있는 모든 열거형 멤버에 대 한 열거형 값 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="9b4d1-110">지정된 된 형식의와 호환 되 변수의 형식을 개체 여부를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="9b4d1-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="9b4d1-111">사용 하 여는 `TypeOf` 연산자와 조합 하는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 사용 하 여 개체를 테스트 하는 `TypeOf`... `Is` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="9b4d1-112">`TypeOf`... `Is` 식 반환 `True` 개체의 런타임 형식이 호환 되는지 지정 된 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="9b4d1-113">호환성에 대 한 조건 클래스, 구조체 또는 인터페이스에 지정된 된 형식 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="9b4d1-114">일반적으로 개체와 동일한 형식이에서 상속 하거나 지정 된 형식을 구현 하는 형식은 호환있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="9b4d1-115">자세한 내용은 참조 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b4d1-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9b4d1-116">Compiling the Code</span></span>  
 <span data-ttu-id="9b4d1-117">참고는 지정된 된 형식의 변수 또는 식이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="9b4d1-118">클래스, 구조체 또는 인터페이스와 같은 정의 된 형식의 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="9b4d1-119">여기에 내장 형식이 같은 `Integer` 및 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4d1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b4d1-120">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [<span data-ttu-id="9b4d1-121">개체 변수</span><span class="sxs-lookup"><span data-stu-id="9b4d1-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="9b4d1-122">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="9b4d1-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="9b4d1-123">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9b4d1-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
