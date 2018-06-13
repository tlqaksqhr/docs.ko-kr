---
title: 정적 생성자(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 52c52f68bc3612807b810047044aedbd2c457cf1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315713"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="c82a3-102">정적 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c82a3-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="c82a3-103">정적 생성자는 [정적](../../../csharp/language-reference/keywords/static.md) 데이터를 초기화하거나 한 번만 수행해야 하는 특정 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="c82a3-104">첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 <span data-ttu-id="c82a3-105">정적 생성자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-105">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="c82a3-106">정적 생성자는 액세스 한정자를 사용하거나 매개 변수를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="c82a3-107">정적 생성자는 첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출되어 [클래스](../../../csharp/language-reference/keywords/class.md)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="c82a3-108">정적 생성자는 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-108">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="c82a3-109">사용자는 프로그램에서 정적 생성자가 실행되는 시기를 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="c82a3-110">정적 생성자는 일반적으로 클래스가 로그 파일을 사용하고, 생성자를 사용하여 이 파일에 항목을 쓰는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="c82a3-111">정적 생성자는 생성자가 `LoadLibrary` 메서드를 호출할 수 있을 때 비관리 코드에 대한 래퍼 클래스를 만드는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="c82a3-112">정적 생성자가 예외를 throw하는 경우 런타임에서 생성자를 다시 호출하지 않으며, 프로그램을 실행 중인 응용 프로그램 도메인의 수명 동안 형식이 초기화되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c82a3-113">예</span><span class="sxs-lookup"><span data-stu-id="c82a3-113">Example</span></span>  
 <span data-ttu-id="c82a3-114">이 예제에서 `Bus` 클래스에는 정적 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="c82a3-115">`Bus`의 첫 번째 인스턴스를 만들 때(`bus1`) 정적 생성자가 호출되어 클래스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="c82a3-116">샘플 출력은 `Bus`의 두 인스턴스가 생성된 경우에도 정적 생성자가 한 번만 실행되고, 인스턴스 생성자를 실행하기 전에 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c82a3-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c82a3-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c82a3-117">See Also</span></span>  
 [<span data-ttu-id="c82a3-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c82a3-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c82a3-119">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="c82a3-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="c82a3-120">생성자</span><span class="sxs-lookup"><span data-stu-id="c82a3-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="c82a3-121">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="c82a3-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="c82a3-122">종료자</span><span class="sxs-lookup"><span data-stu-id="c82a3-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
