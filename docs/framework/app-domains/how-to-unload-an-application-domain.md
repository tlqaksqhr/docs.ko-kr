---
title: "방법: 응용 프로그램 도메인 언로드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5067651a9cb30602a7318380d469b6f6381d8756
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="76543-102">방법: 응용 프로그램 도메인 언로드</span><span class="sxs-lookup"><span data-stu-id="76543-102">How to: Unload an Application Domain</span></span>
<span data-ttu-id="76543-103">응용 프로그램 도메인 사용을 마쳤으면 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드를 사용하여 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="76543-103">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="76543-104">**Unload** 메서드는 지정된 응용 프로그램 도메인을 정상적으로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="76543-104">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="76543-105">언로드 프로세스 중에는 새 스레드가 응용 프로그램 도메인에 액세스할 수 없으며 모든 응용 프로그램 도메인 특정 데이터 구조가 비워집니다.</span><span class="sxs-lookup"><span data-stu-id="76543-105">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="76543-106">응용 프로그램 도메인에 로드된 어셈블리가 제거되고 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76543-106">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="76543-107">응용 프로그램 도메인의 어셈블리가 도메인 중립적인 경우 해당 어셈블리의 데이터는 전체 프로세스가 종료될 때까지 메모리에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76543-107">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="76543-108">따라서 도메인 중립 어셈블리를 언로드하려면 전체 프로세스를 종료하는 것이 유일한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="76543-108">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="76543-109">경우에 따라 응용 프로그램 도메인에 대한 언로드 요청이 제대로 작동하지 않아 <xref:System.CannotUnloadAppDomainException>이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76543-109">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="76543-110">다음 예제에서는 `MyDomain`이라는 새 응용 프로그램 도메인을 만들고, 콘솔에 일부 정보를 출력한 다음, 해당 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="76543-110">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="76543-111">이 코드에서는 언로드된 응용 프로그램 도메인의 이름을 콘솔에 출력하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="76543-111">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="76543-112">이 동작은 프로그램 끝에 있는 try/catch 문으로 처리되는 예외를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="76543-112">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76543-113">예</span><span class="sxs-lookup"><span data-stu-id="76543-113">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="76543-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76543-114">See Also</span></span>  
 [<span data-ttu-id="76543-115">응용 프로그램 도메인으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="76543-115">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="76543-116">방법: 응용 프로그램 도메인 만들기</span><span class="sxs-lookup"><span data-stu-id="76543-116">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 [<span data-ttu-id="76543-117">응용 프로그램 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="76543-117">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
