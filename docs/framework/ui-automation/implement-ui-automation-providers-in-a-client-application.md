---
title: "클라이언트 응용 프로그램에서 UI 자동화 공급자 구현"
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
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
caps.latest.revision: "6"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: c099cd74b14160ca69bda5b353c7bbd7e3327cd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="f3998-102">클라이언트 응용 프로그램에서 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="f3998-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="f3998-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3998-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f3998-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3998-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f3998-105">이 항목에는 응용 프로그램 내에서 클라이언트 쪽 UI 자동화 공급자를 구현하는 방법을 보여 주는 예제 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3998-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="f3998-106">이 방법은 일반적인 시나리오는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f3998-106">This is an uncommon scenario.</span></span> <span data-ttu-id="f3998-107">대부분의 경우, UI 자동화 클라이언트 응용 프로그램은 서버 쪽 공급자 또는 DLL에 상주하는 클라이언트 쪽 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3998-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3998-108">예</span><span class="sxs-lookup"><span data-stu-id="f3998-108">Example</span></span>  
 <span data-ttu-id="f3998-109">다음 코드 예제에서는 콘솔 창에 대한 간단한 공급자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f3998-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="f3998-110">이 코드에는 유용한 기능이 없지만, 클라이언트 코드 내에서 공급자를 설정하고 <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>을 사용하여 공급자를 등록하는 기본적인 단계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3998-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="f3998-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3998-111">See Also</span></span>  
 [<span data-ttu-id="f3998-112">UI 자동화 공급자 개요</span><span class="sxs-lookup"><span data-stu-id="f3998-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="f3998-113">클라이언트 쪽 공급자 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="f3998-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)  
 [<span data-ttu-id="f3998-114">클라이언트 쪽 UI 자동화 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="f3998-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)  
 [<span data-ttu-id="f3998-115">클라이언트 쪽 UI 자동화 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="f3998-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
