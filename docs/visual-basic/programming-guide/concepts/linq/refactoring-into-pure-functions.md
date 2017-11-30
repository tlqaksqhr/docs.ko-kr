---
title: "(Visual Basic) 순수 함수로 리팩터링"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d0a1b8d314cf1403ef5065e5432f7acd15ebb440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="refactoring-into-pure-functions-visual-basic"></a><span data-ttu-id="ce546-102">(Visual Basic) 순수 함수로 리팩터링</span><span class="sxs-lookup"><span data-stu-id="ce546-102">Refactoring Into Pure Functions (Visual Basic)</span></span>
<span data-ttu-id="ce546-103">순수 함수 변환의 중요한 측면은 순수 함수를 사용하여 코드를 리팩터링하는 방법을 습득하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
 <span data-ttu-id="ce546-104">이 단원의 앞 부분에서 설명한 것처럼 순수 함수에는 두 가지 유용한 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-104">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
-   <span data-ttu-id="ce546-105">순수 함수는 의도하지 않은 결과를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-105">It has no side effects.</span></span> <span data-ttu-id="ce546-106">함수는 함수 외부에 있는 형식의 데이터나 변수를 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-106">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
-   <span data-ttu-id="ce546-107">순수 함수는 일관성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-107">It is consistent.</span></span> <span data-ttu-id="ce546-108">동일한 입력 데이터의 집합이 제공되는 경우 항상 동일한 출력 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-108">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="ce546-109">함수형 프로그래밍으로 전환하는 한 가지 방법은 기존 코드를 리팩터링하여 의도하지 않은 불필요한 결과와 외부 종속성을 없애는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-109">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="ce546-110">이런 식으로 기존 코드의 순수 함수 버전을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-110">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="ce546-111">이 항목에서는 순수 함수의 개념과 순수 함수가 의미하지 않는 것에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-111">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="ce546-112">[자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) 자습서 WordprocessingML 문서를 조작 하는 방법을 보여 주고 순수 함수를 사용 하 여 리팩터링 하는 방법의 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-112">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="ce546-113">의도하지 않은 결과 및 외부 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="ce546-113">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="ce546-114">다음 예제에서는 두 가지 비순수 함수와 순수 함수를 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-114">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="ce546-115">클래스 멤버를 변경하는 비순수 함수</span><span class="sxs-lookup"><span data-stu-id="ce546-115">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="ce546-116">다음 코드에서 `HypenatedConcat` 함수는 클래스에서 `aMember` 데이터 멤버를 수정하기 때문에 순수 함수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-116">In the following code, the `HypenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
```vb  
Module Module1  
    Dim aMember As String = "StringOne"  
  
    Public Sub HypenatedConcat(ByVal appendStr As String)  
        aMember = aMember & "-" & appendStr  
    End Sub  
  
    Sub Main()  
        HypenatedConcat("StringTwo")  
        Console.WriteLine(aMember)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ce546-117">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-117">This code produces the following output:</span></span>  
  
```  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="ce546-118">아닌지 관련 수정 되는 데이터가 있는지 여부는 참고 `public` 또는 `private` 되었거나, 액세스 한 `shared` 멤버 또는 인스턴스 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-118">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a  `shared` member or an instance member.</span></span> <span data-ttu-id="ce546-119">순수 함수는 함수 외부에 있는 데이터를 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-119">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="ce546-120">인수를 변경하는 비순수 함수</span><span class="sxs-lookup"><span data-stu-id="ce546-120">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="ce546-121">또한 이 동일한 함수의 다음 버전은 매개 변수 `sb`의 내용을 수정하기 때문에 순수 함수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-121">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
```vb  
Module Module1  
    Public Sub HypenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)  
        sb.Append("-" & appendStr)  
    End Sub  
  
    Sub Main()  
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")  
        HypenatedConcat(sb1, "StringTwo")  
        Console.WriteLine(sb1)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ce546-122">`HypenatedConcat` 함수가 <xref:System.Text.StringBuilder.Append%2A> 멤버 함수를 호출하여 첫 번째 매개 변수의 값(상태)을 변경했기 때문에 이 프로그램 버전은 첫 번째 버전과 동일한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-122">This version of the program produces the same output as the first version, because the `HypenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="ce546-123">이러한 변경은 `HypenatedConcat`에서 값에 의한 호출(call-by-value) 매개 변수 전달을 사용함에도 불구하고 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-123">Note that this alteration occurs despite that fact that `HypenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce546-124">참조 형식의 경우 값에 의해 매개 변수를 전달하면 개체에 대한 참조의 복사본이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-124">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="ce546-125">이 복사본은 참조 변수가 새 개체에 할당될 때까지 원래 참조와 동일한 인스턴스 데이터와 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-125">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="ce546-126">참조에 의한 호출(call-by-reference)을 사용하는 경우 함수에서 반드시 매개 변수를 수정해야 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-126">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="ce546-127">순수 함수</span><span class="sxs-lookup"><span data-stu-id="ce546-127">Pure Function</span></span>  
 <span data-ttu-id="ce546-128">이 다음 버전의 프로그램에서는 `HypenatedConcat` 함수를 순수 함수로 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-128">This next version of the program hows how to implement the `HypenatedConcat` function as a pure function.</span></span>  
  
```vb  
Module Module1  
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String  
        Return (s & "-" & appendStr)  
    End Function  
  
    Sub Main()  
        Dim s1 As String = "StringOne"  
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")  
        Console.WriteLine(s2)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ce546-129">이 버전은 동일한 출력 `StringOne-StringTwo`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-129">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="ce546-130">연결된 값을 유지하기 위해 해당 값은 중간 변수 `s2`에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-130">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="ce546-131">매우 유용할 수 있는 한 가지 방법은 로컬로는 순수하지 않지만(즉, 지역 변수를 선언하고 수정함) 전역적으로는 순수한 함수를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-131">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="ce546-132">이러한 함수는 유용한 조합성(composability) 특징을 많이 갖고 있지만 간단한 루프가 동일한 작업을 수행하는 경우 재귀를 사용해야 하는 등의 더욱 꼬인(convoluted) 함수형 프로그래밍 특징을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-132">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="ce546-133">표준 쿼리 연산자</span><span class="sxs-lookup"><span data-stu-id="ce546-133">Standard Query Operators</span></span>  
 <span data-ttu-id="ce546-134">표준 쿼리 연산자의 중요한 특징은 순수 함수로 구현된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-134">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="ce546-135">자세한 내용은 참조 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce546-135">For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce546-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce546-136">See Also</span></span>  
 [<span data-ttu-id="ce546-137">순수 함수 변환 (Visual Basic) 소개</span><span class="sxs-lookup"><span data-stu-id="ce546-137">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [<span data-ttu-id="ce546-138">함수형 프로그래밍과 명령형 프로그래밍 비교 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce546-138">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
