---
title: '방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5f7ae6bae46cdf6596b206abbdeeb94b5c21a13f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332188"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="4d86f-102">방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4d86f-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="4d86f-103">이 예제에서는 [interface](../../../csharp/language-reference/keywords/interface.md) `IDimensions` 및 `Box` 클래스를 선언합니다. 이 클래스는 인터페이스 멤버 `getLength` 및 `getWidth`를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4d86f-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="4d86f-104">멤버는 인터페이스 인스턴스 `dimensions`를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4d86f-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d86f-105">예</span><span class="sxs-lookup"><span data-stu-id="4d86f-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="4d86f-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4d86f-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="4d86f-107">`Main` 메서드의 다음 줄은 컴파일 오류를 생성하므로 주석으로 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d86f-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="4d86f-108">명시적으로 구현된 인터페이스 멤버는 [class](../../../csharp/language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d86f-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   <span data-ttu-id="4d86f-109">또한 `Main` 메서드의 다음 줄은 메서드가 인터페이스 인스턴스에서 호출되기 때문에 상자 크기를 성공적으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d86f-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4d86f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d86f-110">See Also</span></span>  
 [<span data-ttu-id="4d86f-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4d86f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4d86f-112">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="4d86f-112">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="4d86f-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d86f-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="4d86f-114">방법: 두 인터페이스의 멤버를 명시적으로 구현</span><span class="sxs-lookup"><span data-stu-id="4d86f-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
