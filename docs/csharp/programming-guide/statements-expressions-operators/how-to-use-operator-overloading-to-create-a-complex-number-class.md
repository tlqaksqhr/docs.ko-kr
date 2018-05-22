---
title: '방법: 연산자 오버로딩을 사용하여 복소수 클래스 만들기(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
ms.openlocfilehash: d746355dac1b99690a5a94c829bd35598c6c8be8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="83da3-102">방법: 연산자 오버로딩을 사용하여 복소수 클래스 만들기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="83da3-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="83da3-103">이 예제에서는 연산자 오버로드를 사용하여 복합 더하기를 정의하는 복소수 클래스 `Complex`를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83da3-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="83da3-104">이 프로그램은 `ToString` 메서드 재정의를 사용하여 숫자의 허수부 및 실수부와 더하기 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="83da3-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83da3-105">예</span><span class="sxs-lookup"><span data-stu-id="83da3-105">Example</span></span>  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="83da3-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83da3-106">See Also</span></span>  
 [<span data-ttu-id="83da3-107">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="83da3-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="83da3-108">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="83da3-108">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="83da3-109">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="83da3-109">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 <span data-ttu-id="83da3-110">[Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)(오버로드된 연산자가 C#에서 항상 정적인 이유)</span><span class="sxs-lookup"><span data-stu-id="83da3-110">[Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)</span></span>
