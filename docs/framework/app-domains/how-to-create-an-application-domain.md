---
title: "방법: 응용 프로그램 도메인 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 39d8db32f82827e76d9517d387e2fc001fc209aa
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="1ab3d-102">방법: 응용 프로그램 도메인 만들기</span><span class="sxs-lookup"><span data-stu-id="1ab3d-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="1ab3d-103">공용 언어 런타임 호스트는 필요할 때 자동으로 응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1ab3d-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="1ab3d-104">그러나 사용자 고유의 응용 프로그램 도메인을 만들고 개인적으로 관리하려는 어셈블리를 해당 도메인에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab3d-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="1ab3d-105">코드를 실행할 응용 프로그램 도메인을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab3d-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="1ab3d-106"><xref:System.AppDomain?displayProperty=fullName> 클래스에 오버로드된 **CreateDomain** 메서드 중 하나를 사용하여 새 응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1ab3d-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=fullName> class.</span></span> <span data-ttu-id="1ab3d-107">응용 프로그램 도메인에 이름을 지정하고 해당 이름으로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ab3d-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="1ab3d-108">다음 예제에서는 새 응용 프로그램 도메인을 만들고, 이름 `MyDomain`을 할당한 다음 호스트 도메인 및 새로 만든 자식 응용 프로그램 도메인의 이름을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab3d-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ab3d-109">예제</span><span class="sxs-lookup"><span data-stu-id="1ab3d-109">Example</span></span>  
 <span data-ttu-id="1ab3d-110">[!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="1ab3d-110">[!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)] [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)] [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab3d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ab3d-111">See Also</span></span>  
 <span data-ttu-id="1ab3d-112">[응용 프로그램 도메인으로 프로그래밍](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="1ab3d-112">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 [<span data-ttu-id="1ab3d-113">응용 프로그램 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="1ab3d-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)

