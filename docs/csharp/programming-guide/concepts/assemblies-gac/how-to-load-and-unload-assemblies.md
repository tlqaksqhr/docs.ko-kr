---
title: "방법: 어셈블리 로드 및 언로드(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4b7c9e257a1fff6236770ff39f5d26cd97224b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="47a69-102">방법: 어셈블리 로드 및 언로드(C#)</span><span class="sxs-lookup"><span data-stu-id="47a69-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="47a69-103">프로그램에서 참조하는 어셈블리는 빌드 시 자동으로 로드되지만, 런타임에 현재 응용 프로그램 도메인에 특정 어셈블리를 로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="47a69-104">자세한 내용은 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47a69-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="47a69-105">해당 어셈블리가 포함된 응용 프로그램 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="47a69-106">어셈블리가 범위를 벗어난 경우에도 실제 어셈블리 파일은 해당 파일을 포함하는 응용 프로그램 도메인이 모두 언로드될 때까지 로드된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="47a69-107">일부 어셈블리만 언로드하고 다른 어셈블리는 언로드하지 않으려는 경우 새 응용 프로그램 도메인을 만들고, 이 도메인 내에서 코드를 실행한 다음 해당 응용 프로그램 도메인을 언로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="47a69-108">자세한 내용은 [방법: 응용 프로그램 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47a69-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="47a69-109">응용 프로그램 도메인에 어셈블리를 로드하려면</span><span class="sxs-lookup"><span data-stu-id="47a69-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="47a69-110"><xref:System.AppDomain> 및 <xref:System.Reflection> 클래스에 포함된 여러 로드 메서드 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="47a69-111">자세한 내용은 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47a69-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="47a69-112">응용 프로그램 도메인을 언로드하려면</span><span class="sxs-lookup"><span data-stu-id="47a69-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="47a69-113">해당 어셈블리가 포함된 응용 프로그램 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="47a69-114"><xref:System.AppDomain>의 `Unload` 메서드를 사용하여 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="47a69-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="47a69-115">자세한 내용은 [방법: 응용 프로그램 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47a69-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a69-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47a69-116">See Also</span></span>  
 [<span data-ttu-id="47a69-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="47a69-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="47a69-118">어셈블리 및 전역 어셈블리 캐시(C#)</span><span class="sxs-lookup"><span data-stu-id="47a69-118">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="47a69-119">방법: 응용 프로그램 도메인에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="47a69-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
