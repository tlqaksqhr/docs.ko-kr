---
title: 초기 바인딩 및 런타임에 바인딩(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aceffe59fb6043b3089621b9a3f95b0425f9a522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="08ad3-102">초기 바인딩 및 런타임에 바인딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08ad3-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="08ad3-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러는 개체가 개체 변수에 할당될 때 `binding`이라는 프로세스를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="08ad3-104">개체는 특정 개체 형식으로 선언된 변수에 할당되면 *초기 바인딩*됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="08ad3-105">초기 바인딩된 개체는 응용 프로그램이 실행되기 전에 컴파일러가 메모리를 할당하고 기타 최적화를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="08ad3-106">예를 들어 다음 코드 조각에서는 변수를 <xref:System.IO.FileStream> 형식으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 <span data-ttu-id="08ad3-107"><xref:System.IO.FileStream>이 특정 개체 형식이므로 `FS`에 할당된 인스턴스는 초기에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-107">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="08ad3-108">반대로 개체에 `Object` 형식으로 선언된 변수에 할당되면 *런타임에 바인딩*됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-108">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="08ad3-109">이 형식의 개체는 모든 개체에 대한 참조를 유지할 수 있지만 초기 바인딩 개체의 다양한 장점은 제공하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-109">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="08ad3-110">예를 들어 다음 코드 조각에서는 `CreateObject` 함수가 반환하는 개체를 포함하도록 개체 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-110">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="08ad3-111">초기 바인딩의 장점</span><span class="sxs-lookup"><span data-stu-id="08ad3-111">Advantages of Early Binding</span></span>  
 <span data-ttu-id="08ad3-112">초기 바인딩된 개체는 컴파일러가 보다 효율적인 응용 프로그램을 생성하는 중요한 최적화를 수행할 수 있도록 하므로 가능한 경우 항상 초기 바인딩된 개체를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-112">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="08ad3-113">초기 바인딩된 개체는 런타임에 바인딩된 개체보다 훨씬 더 빠르며, 사용되는 개체 종류를 정확히 언급하여 코드를 보다 쉽게 읽고 유지 관리하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-113">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="08ad3-114">초기 바인딩의 또 다른 장점은 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE(통합 개발 환경)가 코드를 편집할 때 작업하는 개체의 형식을 정확히 파악할 수 있으므로 자동 코드 완성 및 동적 도움말 같은 유용한 기능을 사용할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="08ad3-115">초기 바인딩의 경우 프로그램이 컴파일될 때 컴파일러가 오류를 보고할 수 있으므로 런타임 오류의 수와 심각도도 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-115">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08ad3-116">런타임에 바인딩은 `Public`으로 선언된 형식 멤버에 액세스하는 데만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-116">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="08ad3-117">`Friend` 또는 `Protected Friend`로 선언된 멤버에 액세스하면 런타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad3-117">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ad3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08ad3-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [<span data-ttu-id="08ad3-119">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="08ad3-119">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="08ad3-120">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="08ad3-120">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
