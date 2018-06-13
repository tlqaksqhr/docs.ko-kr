---
title: Of 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: 9ace0ad55d9eb1618dbdafb0d49d1ff4b169a877
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603953"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="7b8e2-102">Of 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b8e2-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="7b8e2-103">소개는 `Of` 절 하 게 식별 하는 *형식 매개 변수* 에 *제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="7b8e2-104">제네릭 형식에 대 한 자세한 내용은 참조 하십시오. [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="7b8e2-105">사용 하는 키워드의</span><span class="sxs-lookup"><span data-stu-id="7b8e2-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="7b8e2-106">다음 코드 예제에서는 `Of` 두 형식 매개 변수를 사용 하는 클래스의 윤곽선을 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="7b8e2-107">것 *제한* 는 `keyType` 하 여 매개 변수는 <xref:System.IComparable> 인터페이스를 사용 하는 코드를 구현 하는 형식 인수를 제공 해야 통해 <xref:System.IComparable>합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="7b8e2-108">이 작업은 필요 하는 `add` 프로시저를 호출할 수는 <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7b8e2-109">제약 조건에 대 한 자세한 내용은 참조 하십시오. [유형 목록](../../../visual-basic/language-reference/statements/type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="7b8e2-110">이전 클래스 정의 완료 하면 다양 한를 생성할 수 있습니다 `dictionary` 에서 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="7b8e2-111">에 제공한 형식 `entryType` 및 `keyType` 어떤 유형의 항목 클래스를 보유 하 고 어떤 유형의 키에 연결 되는 각 항목을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="7b8e2-112">제약 조건,를에 제공 해야 `keyType` 구현 하는 형식을 <xref:System.IComparable>합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="7b8e2-113">다음 코드 예제에서는 보유 하는 개체를 만듭니다. `String` 항목과 연결 된 `Integer` 키를 각 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="7b8e2-114">`Integer` 구현 <xref:System.IComparable> 따라서에 제약 조건을 만족 하 고 `keyType`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="7b8e2-115">`Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b8e2-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="7b8e2-116">Class 문</span><span class="sxs-lookup"><span data-stu-id="7b8e2-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="7b8e2-117">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="7b8e2-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="7b8e2-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="7b8e2-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="7b8e2-119">Interface 문</span><span class="sxs-lookup"><span data-stu-id="7b8e2-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="7b8e2-120">Structure 문</span><span class="sxs-lookup"><span data-stu-id="7b8e2-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="7b8e2-121">Sub 문</span><span class="sxs-lookup"><span data-stu-id="7b8e2-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b8e2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b8e2-122">See Also</span></span>  
 <xref:System.IComparable>  
 [<span data-ttu-id="7b8e2-123">형식 목록</span><span class="sxs-lookup"><span data-stu-id="7b8e2-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="7b8e2-124">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="7b8e2-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="7b8e2-125">In</span><span class="sxs-lookup"><span data-stu-id="7b8e2-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="7b8e2-126">Out</span><span class="sxs-lookup"><span data-stu-id="7b8e2-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
