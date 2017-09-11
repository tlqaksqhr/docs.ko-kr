---
title: "방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 88b96c15f724ee5961c72917308138a045988225
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="b7853-102">방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b7853-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="b7853-103">이 예제에서는 [interface](../../../csharp/language-reference/keywords/interface.md) `IDimensions` 및 `Box` 클래스를 선언합니다. 이 클래스는 인터페이스 멤버 `getLength` 및 `getWidth`를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b7853-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="b7853-104">멤버는 인터페이스 인스턴스 `dimensions`를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="b7853-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7853-105">예제</span><span class="sxs-lookup"><span data-stu-id="b7853-105">Example</span></span>  
 <span data-ttu-id="b7853-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b7853-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b7853-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b7853-107">Robust Programming</span></span>  
  
-   <span data-ttu-id="b7853-108">`Main` 메서드의 다음 줄은 컴파일 오류를 생성하므로 주석으로 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7853-108">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="b7853-109">명시적으로 구현된 인터페이스 멤버는 [class](../../../csharp/language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7853-109">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     <span data-ttu-id="b7853-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b7853-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span></span>  
  
-   <span data-ttu-id="b7853-111">또한 `Main` 메서드의 다음 줄은 메서드가 인터페이스 인스턴스에서 호출되기 때문에 상자 크기를 성공적으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7853-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     <span data-ttu-id="b7853-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b7853-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7853-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7853-113">See Also</span></span>  
 <span data-ttu-id="b7853-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b7853-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b7853-115">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="b7853-115">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="b7853-116">[인터페이스](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="b7853-116">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="b7853-117">방법: 두 인터페이스의 멤버를 명시적으로 구현</span><span class="sxs-lookup"><span data-stu-id="b7853-117">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)

