---
title: "방법: 어셈블리 로드 및 언로드(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6bf6de24f4cbc3f3bd855b6d2cafa8120ebd90ee
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="21088-102">방법: 어셈블리 로드 및 언로드(C#)</span><span class="sxs-lookup"><span data-stu-id="21088-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="21088-103">프로그램에서 참조하는 어셈블리는 빌드 시 자동으로 로드되지만, 런타임에 현재 응용 프로그램 도메인에 특정 어셈블리를 로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21088-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="21088-104">자세한 내용은 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21088-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="21088-105">해당 어셈블리가 포함된 응용 프로그램 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21088-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="21088-106">어셈블리가 범위를 벗어난 경우에도 실제 어셈블리 파일은 해당 파일을 포함하는 응용 프로그램 도메인이 모두 언로드될 때까지 로드된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="21088-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="21088-107">일부 어셈블리만 언로드하고 다른 어셈블리는 언로드하지 않으려는 경우 새 응용 프로그램 도메인을 만들고, 이 도메인 내에서 코드를 실행한 다음 해당 응용 프로그램 도메인을 언로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="21088-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="21088-108">자세한 내용은 [방법: 응용 프로그램 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21088-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="21088-109">응용 프로그램 도메인에 어셈블리를 로드하려면</span><span class="sxs-lookup"><span data-stu-id="21088-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="21088-110"><xref:System.AppDomain> 및 <xref:System.Reflection> 클래스에 포함된 여러 로드 메서드 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21088-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="21088-111">자세한 내용은 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21088-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="21088-112">응용 프로그램 도메인을 언로드하려면</span><span class="sxs-lookup"><span data-stu-id="21088-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="21088-113">해당 어셈블리가 포함된 응용 프로그램 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21088-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="21088-114"><xref:System.AppDomain>의 `Unload` 메서드를 사용하여 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="21088-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="21088-115">자세한 내용은 [방법: 응용 프로그램 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21088-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21088-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21088-116">See Also</span></span>  
 <span data-ttu-id="21088-117">[C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="21088-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="21088-118">[어셈블리 및 전역 어셈블리 캐시(C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="21088-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 [<span data-ttu-id="21088-119">방법: 응용 프로그램 도메인에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="21088-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)

