---
title: "익명 형식 정의(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="ca166-102">익명 형식 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca166-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="ca166-103">익명 형식의 인스턴스 선언에 대 한 응답, 컴파일러는 형식에 대 한 지정 된 속성을 포함 하는 새 클래스 정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="ca166-104">컴파일러에서 생성 된 코드</span><span class="sxs-lookup"><span data-stu-id="ca166-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="ca166-105">다음과 같이 정의 대 한 `product`, 컴파일러는 속성을 포함 하는 새 클래스 정의 만듭니다 `Name`, `Price`, 및 `OnHand`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 <span data-ttu-id="ca166-106">클래스 정의 다음과 유사한 속성 정의 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="ca166-107">없는 `Set` 키 속성에 대 한 메서드.</span><span class="sxs-lookup"><span data-stu-id="ca166-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="ca166-108">키 속성의 값은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-108">The values of key properties are read-only.</span></span>  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 <span data-ttu-id="ca166-109">또한 익명 형식 정의 기본 생성자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="ca166-110">매개 변수를 필요로 하는 생성자는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="ca166-111">형식 정의에서 상속 되며, 세 가지 멤버를 재정의 무명 형식 선언 키 속성이 하나 이상 들어 있을 경우 <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="ca166-112">만 키 속성이 없는 선언 된 경우 <xref:System.Object.ToString%2A> 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="ca166-113">재정의 다음 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="ca166-114">`Equals`반환 `True` 두 익명 형식 인스턴스는 동일한 인스턴스 또는 다음 조건을 충족 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ca166-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="ca166-115">동일한 수의 속성을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="ca166-116">동일한 순서로 동일한 이름 가진 속성이 선언 되 고 유추 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="ca166-117">이름을 비교할 때는 대/소문자 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="ca166-118">키 속성은 속성 중 하나 이상 및 `Key` 키워드는 동일한 속성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="ca166-119">키 속성의 각 해당 쌍의 비교 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="ca166-120">예를 들어 다음 예제에서에서 `Equals` 반환 `True` 에 대해서만 `employee01` 및 `employee08`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="ca166-121">새 인스턴스 일치 하지 않는 이유를 지정 하는 각 줄 앞의 주석이 `employee01`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   <span data-ttu-id="ca166-122">`GetHashcode`적절 하 게 고유 GetHashCode 알고리즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="ca166-123">알고리즘 해시 코드를 계산 하는 키 속성만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="ca166-124">`ToString`다음 예제와 같이 연결 된 속성 값의 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="ca166-125">키와 키가 아닌 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 <span data-ttu-id="ca166-126">익명 형식을 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="ca166-127">사용할 수 없습니다, 즉 `.Equals`, `.GetHashCode`, 또는 `.ToString` 속성 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="ca166-128">익명 형식 정의 하나 이상 포함 하는 키 속성이 구현은 <xref:System.IEquatable%601?displayProperty=nameWithType> 인터페이스를 여기서 `T` 유형 익명 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca166-129">익명 형식 선언 동일한 어셈블리에서 발생 하는, 동일한 이름을 갖는 및 유추 된 형식, 같은 순서로 속성이 선언 되 고 동일한 속성이 키 속성으로 표시 됩니다 경우에 동일한 익명 형식의 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca166-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca166-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca166-130">See Also</span></span>  
 [<span data-ttu-id="ca166-131">익명 형식</span><span class="sxs-lookup"><span data-stu-id="ca166-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="ca166-132">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="ca166-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
