---
title: COM 래퍼
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 60f5acf6ed8a7fe0bb2e6293666c33a479d25643
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="com-wrappers"></a><span data-ttu-id="8068e-102">COM 래퍼</span><span class="sxs-lookup"><span data-stu-id="8068e-102">COM Wrappers</span></span>
<span data-ttu-id="8068e-103">COM은 다음과 같은 여러 중요한 방식에서 .NET Framework 개체 모델과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
-   <span data-ttu-id="8068e-104">COM 개체의 클라이언트는 이러한 개체의 수명을 관리해야 합니다. 공용 언어 런타임은 해당 환경에서 개체의 수명을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
-   <span data-ttu-id="8068e-105">COM 개체의 클라이언트는 해당 서비스를 제공하는 인터페이스를 요청하고 다시 인터페이스 포인터를 가져와 서비스를 사용할 수 있는지 여부를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="8068e-106">.NET 개체의 클라이언트는 리플렉션을 사용하여 개체의 기능에 대한 설명을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
-   <span data-ttu-id="8068e-107">NET 개체는 .NET Framework 실행 환경에서 관리하는 메모리에 상주합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="8068e-108">실행 환경은 성능상의 이유로 메모리에서 개체를 이동하고, 이동되는 개체에 대한 모든 참조를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="8068e-109">개체에 대한 포인터가 있는, 관리되지 않는 클라이언트의 경우 개체가 동일한 위치에 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="8068e-110">이러한 클라이언트에는 위치가 고정되지 않은 개체를 처리하는 메커니즘이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="8068e-111">이러한 차이점을 극복하기 위해 런타임은 관리되는 클라이언트와 관리되지 않는 클라이언트 둘 다가 해당 환경 내에서 개체를 호출한다고 여기도록 래퍼 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="8068e-112">관리되는 클라이언트가 COM 개체에 대해 메서드를 호출할 때마다 런타임은 RCW([런타임 호출 가능 래퍼](runtime-callable-wrapper.md))를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="8068e-113">RCW는 무엇보다도 관리되는 참조 메커니즘과 관리되지 않는 참조 메커니즘 간의 차이점을 추상화합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="8068e-114">또한 런타임은 CCW([COM 호출 가능 래퍼](com-callable-wrapper.md))를 만들어 프로세스를 반대로 하고 COM 클라이언트가 .NET 개체에 대해 메서드를 원활하게 호출할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-114">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="8068e-115">다음 그림과 같이 호출하는 코드의 관점에 따라 런타임이 만드는 래퍼 클래스가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 <span data-ttu-id="8068e-116">![COM 래퍼 개요](media/bidirectional.gif "양방향")</span><span class="sxs-lookup"><span data-stu-id="8068e-116">![COM wrapper overview](media/bidirectional.gif "bidirectional")</span></span>  
<span data-ttu-id="8068e-117">COM 래퍼 개요</span><span class="sxs-lookup"><span data-stu-id="8068e-117">COM wrapper overview</span></span>  
  
 <span data-ttu-id="8068e-118">대부분의 경우 런타임에 의해 생성된 표준 RCW 또는 CCW는 COM 및 .NET Framework 사이의 경계를 넘어가는 호출에 대해 적절한 마샬링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-118">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="8068e-119">사용자 지정 특성을 사용하여 런타임이 관리 코드와 비관리 코드를 나타내는 방식을 필요에 따라 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8068e-119">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8068e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8068e-120">See Also</span></span>  
 <span data-ttu-id="8068e-121">[고급 COM 상호 운용성](https://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8068e-121">[Advanced COM Interoperability](https://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb(v=vs.100))</span></span>  
 [<span data-ttu-id="8068e-122">런타임 호출 가능 래퍼</span><span class="sxs-lookup"><span data-stu-id="8068e-122">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)  
 [<span data-ttu-id="8068e-123">COM 호출 가능 래퍼</span><span class="sxs-lookup"><span data-stu-id="8068e-123">COM Callable Wrapper</span></span>](com-callable-wrapper.md)  
 <span data-ttu-id="8068e-124">[표준 래퍼 사용자 지정](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8068e-124">[Customizing Standard Wrappers](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))</span></span>  
 <span data-ttu-id="8068e-125">[방법: 런타임 호출 가능 래퍼 사용자 지정](https://msdn.microsoft.com/library/4a4bb3da-4d60-4517-99f2-78d46a681732(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8068e-125">[How to: Customize Runtime Callable Wrappers](https://msdn.microsoft.com/library/4a4bb3da-4d60-4517-99f2-78d46a681732(v=vs.100))</span></span>
