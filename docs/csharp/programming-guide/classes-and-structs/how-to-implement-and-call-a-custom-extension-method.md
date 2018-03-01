---
title: "방법: 사용자 지정 확장명 메서드 구현 및 호출(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a277412c69d26f20721381d9cfa839c7f082f2f2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="84222-102">방법: 사용자 지정 확장명 메서드 구현 및 호출(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="84222-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="84222-103">이 항목에서는 모든 .NET 형식에 대한 사용자 고유의 확장 메서드를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84222-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="84222-104">클라이언트 코드는 확장 메서드를 포함하는 DLL에 대한 참조를 추가하고 확장 메서드가 정의된 네임스페이스를 지정하는 [using](../../../csharp/language-reference/keywords/using-directive.md) 지시문을 추가하여 확장 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="84222-105">확장 메서드를 정의하고 호출하려면</span><span class="sxs-lookup"><span data-stu-id="84222-105">To define and call the extension method</span></span>  
  
1.  <span data-ttu-id="84222-106">확장 메서드가 포함될 정적 [클래스](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="84222-107">클래스가 클라이언트 코드에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-107">The class must be visible to client code.</span></span> <span data-ttu-id="84222-108">액세스 가능성 규칙에 대한 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84222-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2.  <span data-ttu-id="84222-109">최소한 포함하는 클래스와 동일한 표시 유형으로 확장 메서드를 정적 메서드로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3.  <span data-ttu-id="84222-110">메서드의 첫 번째 매개 변수는 메서드가 작동하는 형식을 지정합니다. [this](../../../csharp/language-reference/keywords/this.md) 한정자가 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4.  <span data-ttu-id="84222-111">호출 코드에 `using` 지시문을 추가하여 확장 메서드 클래스를 포함하는 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5.  <span data-ttu-id="84222-112">형식의 인스턴스 메서드인 것처럼 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="84222-113">연산자가 적용되는 형식을 나타내기 때문에 첫 번째 매개 변수는 호출 코드에서 지정되지 않고 컴파일러가 개체 형식을 이미 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="84222-114">매개 변수 2 ~ `n`에 대한 인수만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84222-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84222-115">예</span><span class="sxs-lookup"><span data-stu-id="84222-115">Example</span></span>  
 <span data-ttu-id="84222-116">다음 예제에서는 `CustomExtensions.StringExtension` 클래스에 `WordCount`라는 확장 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="84222-117">이 메서드는 첫 번째 메서드 매개 변수로 지정된 <xref:System.String> 클래스에 대해 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="84222-118">`CustomExtensions` 네임스페이스를 응용 프로그램 네임스페이스로 가져오고, `Main` 메서드 내부에서 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="84222-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84222-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="84222-119">Compiling the Code</span></span>  
 <span data-ttu-id="84222-120">이 코드를 실행하려면 코드를 복사하여 [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-120">To run this code, copy and paste it into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="84222-121">기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 `using` 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="84222-121">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="84222-122">이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-122">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="84222-123">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="84222-123">.NET Framework Security</span></span>  
 <span data-ttu-id="84222-124">확장 메서드는 특정 보안 취약성은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-124">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="84222-125">형식 자체에서 정의된 인스턴스 또는 정적 메서드를 기준으로 모든 이름 충돌이 해결되기 때문에 확장 메서드를 사용하여 형식의 기존 메서드를 가장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-125">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="84222-126">확장 메서드는 확장된 클래스의 개인 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84222-126">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84222-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84222-127">See Also</span></span>  
 [<span data-ttu-id="84222-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="84222-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="84222-129">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="84222-129">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [<span data-ttu-id="84222-130">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="84222-130">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="84222-131">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="84222-131">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="84222-132">protected</span><span class="sxs-lookup"><span data-stu-id="84222-132">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="84222-133">internal</span><span class="sxs-lookup"><span data-stu-id="84222-133">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 [<span data-ttu-id="84222-134">public</span><span class="sxs-lookup"><span data-stu-id="84222-134">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="84222-135">this</span><span class="sxs-lookup"><span data-stu-id="84222-135">this</span></span>](../../../csharp/language-reference/keywords/this.md)  
 [<span data-ttu-id="84222-136">namespace</span><span class="sxs-lookup"><span data-stu-id="84222-136">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)
