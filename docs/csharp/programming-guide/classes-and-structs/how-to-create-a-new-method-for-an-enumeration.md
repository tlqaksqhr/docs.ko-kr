---
title: '방법: 새 열거형 메서드 만들기(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 8de44cbddf26af45245709d0e28d2d157256ce59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313035"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="adc5c-102">방법: 새 열거형 메서드 만들기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="adc5c-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="adc5c-103">확장 메서드를 사용하여 특정 열거형 형식과 관련된 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adc5c-104">예</span><span class="sxs-lookup"><span data-stu-id="adc5c-104">Example</span></span>  
 <span data-ttu-id="adc5c-105">다음 예제에서 `Grades` 열거형은 학생이 클래스에서 받을 수 있는 문자 성적을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="adc5c-106">해당 형식의 각 인스턴스가 이제 합격 성적을 나타내는지 여부를 "알 수 있도록" `Passing`이라는 확장 메서드가 `Grades` 형식에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 <span data-ttu-id="adc5c-107">또한 `Extensions` 클래스에는 동적으로 업데이트되는 정적 변수가 포함되며, 확장 메서드의 반환 값이 해당 변수의 현재 값을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="adc5c-108">이는 확장 메서드가 정의된 정적 클래스에서 내부적으로 직접 호출됨을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="adc5c-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="adc5c-109">Compiling the Code</span></span>  
 <span data-ttu-id="adc5c-110">이 코드를 실행하려면 코드를 복사하여 Visual Studio에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-110">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="adc5c-111">기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 `using` 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-111">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="adc5c-112">이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc5c-112">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc5c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adc5c-113">See Also</span></span>  
 [<span data-ttu-id="adc5c-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="adc5c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="adc5c-115">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="adc5c-115">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
