---
title: "Windows 스토어 앱 용.NET에 대 한 MEF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8436bff3b6ca1061621a67eb45bdc8aedea33f2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="a2fe1-102">Windows 스토어 앱 용.NET에 대 한 MEF</span><span class="sxs-lookup"><span data-stu-id="a2fe1-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="a2fe1-103"><xref:System.Composition?displayProperty=nameWithType>및 그 하위 네임 스페이스에 확장을 개발 하기 위한 형식이 포함 되어 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱으로 프레임 워크 MEF (Managed Extensibility).</span><span class="sxs-lookup"><span data-stu-id="a2fe1-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="a2fe1-104">이러한 네임 스페이스의 일부인는 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 하위 집합에 대 한는 [!INCLUDE[win8](../../../includes/win8-md.md)] 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="a2fe1-105">이러한 네임 스페이스는.NET Framework와 함께 배포 되는 핵심 클래스 라이브러리에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="a2fe1-106">이러한 네임 스페이스를 설치 하려면에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 에서 **프로젝트** 메뉴 및 선택한 다음 Microsoft.Composition 패키지에 대 한 온라인 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-106">To install these namespaces, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="a2fe1-107"><xref:System.Composition?displayProperty=nameWithType>MEF 핵심을 구성 하는 클래스를 제공에 대 한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="a2fe1-108"><xref:System.Composition.Convention?displayProperty=nameWithType>MEF를 사용 하 여 규칙 기반 구성 모델이 함께 지원 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="a2fe1-109"><xref:System.Composition.Hosting?displayProperty=nameWithType>호스트 응용 프로그램 개발자에 게 유용한 MEF 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="a2fe1-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>컴퍼지션 엔진에서 내부적으로 사용 되는 MEF 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="a2fe1-111">에 대 한 자세한 내용은 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 네임 스페이스 및 형식에 포함 된 목록이 참조 및 [.NET Windows 스토어 앱 용 개요](http://go.microsoft.com/fwlink/p/?LinkID=238312) Windows 개발자 센터에서.</span><span class="sxs-lookup"><span data-stu-id="a2fe1-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](http://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fe1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2fe1-112">See Also</span></span>  
 [<span data-ttu-id="a2fe1-113">.NET Windows 스토어 앱 용 개요</span><span class="sxs-lookup"><span data-stu-id="a2fe1-113">.NET for Windows Store apps overview</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [<span data-ttu-id="a2fe1-114">Windows 스토어 앱용 .NET – 지원되는 API</span><span class="sxs-lookup"><span data-stu-id="a2fe1-114">.NET for Windows Store apps – supported APIs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [<span data-ttu-id="a2fe1-115">MEF(Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="a2fe1-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
