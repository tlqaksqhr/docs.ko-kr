---
title: "방법: 어셈블리 로드 및 언로드 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e38be72bb58573b532fa42a569563df0be8301d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="11768-102">방법: 어셈블리 로드 및 언로드 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11768-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="11768-103">프로그램에서 참조 어셈블리를 빌드 시 자동으로 로드할 수는 있지만 런타임에 현재 응용 프로그램 도메인에 특정 어셈블리를 로드 하도 가능.</span><span class="sxs-lookup"><span data-stu-id="11768-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="11768-104">자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인에 로드 어셈블리](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-104">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
 <span data-ttu-id="11768-105">모든 것을 포함 하는 응용 프로그램 도메인을 언로드하지 않고 개별 어셈블리를 언로드할 수 없는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11768-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="11768-106">어셈블리 범위를 벗어나면 하는 경우에를 포함 하는 모든 응용 프로그램 도메인 로드 될 때까지 실제 어셈블리 파일은 로드 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11768-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="11768-107">일부 어셈블리 일부만 언로드하려면 하려는 경우 새 응용 프로그램 도메인을 만들고 해당 도메인 내의 코드를 실행 한 다음 해당 응용 프로그램 도메인 언로드 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11768-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="11768-108">자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인 언로드](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192)합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-108">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="11768-109">응용 프로그램 도메인에 어셈블리를 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="11768-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="11768-110">클래스와 <xref:System.AppDomain>및 <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain> 에 포함 된 여러 로드 메서드 중 하나를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="11768-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="11768-111">자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인에 로드 어셈블리](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-111">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="11768-112">응용 프로그램 도메인 언로드</span><span class="sxs-lookup"><span data-stu-id="11768-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="11768-113">모든 것을 포함 하는 응용 프로그램 도메인을 언로드하지 않고 개별 어셈블리를 언로드할 수 없는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11768-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="11768-114">사용 된 `Unload` 메서드에서 <xref:System.AppDomain>응용 프로그램 도메인 언로드.</xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="11768-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="11768-115">자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인 언로드](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192)합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-115">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11768-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11768-116">See Also</span></span>  
 <span data-ttu-id="11768-117">[프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="11768-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="11768-118"> [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="11768-118"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="11768-119"> [방법: 응용 프로그램 도메인에 어셈블리를 로드 합니다.](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span><span class="sxs-lookup"><span data-stu-id="11768-119"> [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span></span>
