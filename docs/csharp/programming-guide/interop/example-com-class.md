---
title: "COM 클래스 예제(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
caps.latest.revision: 17
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
ms.openlocfilehash: a759a7dcd211207c8740dd99d592daa509ddec47
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="aa531-102">COM 클래스 예제(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="aa531-102">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="aa531-103">다음은 COM 개체로 노출되는 클래스의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-103">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="aa531-104">이 코드를 .cs 파일에 배치하고 프로젝트에 추가한 후 **COM Interop 등록** 속성을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-104">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="aa531-105">자세한 내용은 [NIB: 방법: 구성 요소 COM Interop 등록](http://msdn.microsoft.com/en-us/4de7d474-56e8-4027-994d-d47ca4725c5e)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa531-105">For more information, see [NIB: How to: Register a Component for COM Interop](http://msdn.microsoft.com/en-us/4de7d474-56e8-4027-994d-d47ca4725c5e).</span></span>  
  
 <span data-ttu-id="aa531-106">Visual C# 개체를 COM에 노출하려면 클래스 인터페이스, 필요한 경우 이벤트 인터페이스 및 클래스 자체를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-106">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="aa531-107">클래스 멤버가 COM에 표시되려면 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-107">Class members must follow these rules to be visible to COM:</span></span>  
  
-   <span data-ttu-id="aa531-108">클래스는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-108">The class must be public.</span></span>  
  
-   <span data-ttu-id="aa531-109">속성, 메서드 및 이벤트는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-109">Properties, methods, and events must be public.</span></span>  
  
-   <span data-ttu-id="aa531-110">속성 및 메서드는 클래스 인터페이스에서 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-110">Properties and methods must be declared on the class interface.</span></span>  
  
-   <span data-ttu-id="aa531-111">이벤트는 이벤트 인터페이스에서 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-111">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="aa531-112">이러한 인터페이스에 선언되지 않은 다른 public 멤버는 COM에 표시되지 않지만 다른 .NET Framework 개체에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-112">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET Framework objects.</span></span>  
  
 <span data-ttu-id="aa531-113">속성 및 메서드를 COM에 노출하려면 클래스 인터페이스에서 선언하고 `DispId` 특성을 사용하여 표시한 후 클래스에서 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-113">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="aa531-114">멤버가 인터페이스에서 선언되는 순서는 COM vtable에 사용되는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-114">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="aa531-115">클래스에서 이벤트를 노출하려면 이벤트 인터페이스에서 선언하고 `DispId` 특성을 사용하여 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-115">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="aa531-116">클래스는 이 인터페이스를 구현하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-116">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="aa531-117">클래스는 클래스 인터페이스를 구현합니다. 둘 이상의 인터페이스를 구현할 수 있지만 첫 번째 구현이 기본 클래스 인터페이스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-117">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="aa531-118">여기에서 COM에 노출된 메서드 및 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-118">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="aa531-119">이러한 메서드 및 속성은 public으로 표시되어야 하며 클래스 인터페이스의 선언과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-119">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="aa531-120">또한 여기에서 클래스에 의해 발생된 이벤트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-120">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="aa531-121">이러한 이벤트는 public으로 표시되어야 하며 이벤트 인터페이스의 선언과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa531-121">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa531-122">예제</span><span class="sxs-lookup"><span data-stu-id="aa531-122">Example</span></span>  
 <span data-ttu-id="aa531-123">[!code-cs[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa531-123">[!code-cs[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa531-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa531-124">See Also</span></span>  
 <span data-ttu-id="aa531-125">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="aa531-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="aa531-126">[상호 운용성](../../../csharp/programming-guide/interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="aa531-126">[Interoperability](../../../csharp/programming-guide/interop/index.md) </span></span>  
 [<span data-ttu-id="aa531-127">프로젝트 디자이너, 빌드 페이지(C#)</span><span class="sxs-lookup"><span data-stu-id="aa531-127">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)

