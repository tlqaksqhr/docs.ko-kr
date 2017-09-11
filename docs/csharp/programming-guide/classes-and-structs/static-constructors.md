---
title: "정적 생성자(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
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
ms.openlocfilehash: 73df76c61f393bf5fe09af66935acfbac4b5663f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="020bc-102">정적 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="020bc-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="020bc-103">정적 생성자는 [정적](../../../csharp/language-reference/keywords/static.md) 데이터를 초기화하거나 한 번만 수행해야 하는 특정 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="020bc-104">첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 <span data-ttu-id="020bc-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="020bc-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="020bc-106">정적 생성자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-106">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="020bc-107">정적 생성자는 액세스 한정자를 사용하거나 매개 변수를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-107">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="020bc-108">정적 생성자는 첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출되어 [클래스](../../../csharp/language-reference/keywords/class.md)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-108">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="020bc-109">정적 생성자는 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-109">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="020bc-110">사용자는 프로그램에서 정적 생성자가 실행되는 시기를 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="020bc-111">정적 생성자는 일반적으로 클래스가 로그 파일을 사용하고, 생성자를 사용하여 이 파일에 항목을 쓰는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="020bc-112">정적 생성자는 생성자가 `LoadLibrary` 메서드를 호출할 수 있을 때 비관리 코드에 대한 래퍼 클래스를 만드는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="020bc-113">정적 생성자가 예외를 throw하는 경우 런타임에서 생성자를 다시 호출하지 않으며, 프로그램을 실행 중인 응용 프로그램 도메인의 수명 동안 형식이 초기화되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="020bc-114">예제</span><span class="sxs-lookup"><span data-stu-id="020bc-114">Example</span></span>  
 <span data-ttu-id="020bc-115">이 예제에서 `Bus` 클래스에는 정적 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="020bc-116">`Bus`의 첫 번째 인스턴스를 만들 때(`bus1`) 정적 생성자가 호출되어 클래스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="020bc-117">샘플 출력은 `Bus`의 두 인스턴스가 생성된 경우에도 정적 생성자가 한 번만 실행되고, 인스턴스 생성자를 실행하기 전에 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="020bc-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 <span data-ttu-id="020bc-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="020bc-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020bc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="020bc-119">See Also</span></span>  
 <span data-ttu-id="020bc-120">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="020bc-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="020bc-121">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="020bc-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="020bc-122">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="020bc-122">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="020bc-123">[정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="020bc-123">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 [<span data-ttu-id="020bc-124">종료자</span><span class="sxs-lookup"><span data-stu-id="020bc-124">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

