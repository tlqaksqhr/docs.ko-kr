---
title: '방법: C#에서 상수 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 03912a71aba883ec9127d265e6f1a2b05e1e60fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="54268-102">방법: C#에서 상수 정의</span><span class="sxs-lookup"><span data-stu-id="54268-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="54268-103">상수는 해당 값이 컴파일 시간에 설정되며 변경할 수 없는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="54268-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="54268-104">상수를 사용하여 특수 값에 대해 숫자 리터럴(“매직 넘버”) 대신 의미 있는 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54268-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54268-105">C#에서는 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 전처리기 지시문을 사용하여 일반적으로 C와 C++에서 사용되는 방식으로 상수를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54268-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="54268-106">정수 형식(`int`, `byte` 등)의 상수 값을 정의하려면 열거 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54268-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="54268-107">자세한 내용은 [enum](../../../csharp/language-reference/keywords/enum.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54268-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="54268-108">정수가 아닌 상수를 정의하는 한 가지 방법은 `Constants`라는 단일 정적 클래스로 그룹화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54268-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="54268-109">이 경우 다음 예제와 같이 상수에 대한 모든 참조 앞에 클래스 이름이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54268-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54268-110">예</span><span class="sxs-lookup"><span data-stu-id="54268-110">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 <span data-ttu-id="54268-111">클래스 이름 한정자를 통해 사용자와 상수를 사용하는 다른 사용자가 상수이며 수정할 수 없음을 쉽게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54268-111">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54268-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54268-112">See Also</span></span>  
 [<span data-ttu-id="54268-113">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="54268-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
