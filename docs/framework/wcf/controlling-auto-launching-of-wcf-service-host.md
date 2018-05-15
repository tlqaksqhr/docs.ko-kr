---
title: WCF 서비스 호스트 자동 시작 제어
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 63c3ca00c0cdc0b28de0fe245b616acd04ca50fe
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="34ccd-102">WCF 서비스 호스트 자동 시작 제어</span><span class="sxs-lookup"><span data-stu-id="34ccd-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="34ccd-103">여러 프로젝트가 포함 된 같은 Visual Studio 솔루션의 다른 프로젝트를 디버깅할 때 WCF 서비스 라이브러리 프로젝트에 대 한 Windows Communication Foundation (WCF) 서비스 호스트 (WcfSvcHost.exe)의 자동 시작 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ccd-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="34ccd-104">이렇게 하려면에서 WCF 서비스 프로젝트를 마우스 오른쪽 단추로 **솔루션 탐색기**, 선택 **속성**를 클릭 하 고 **WCF 옵션** 탭 합니다. **WCF 서비스 호스트 시작 동일한 솔루션의 다른 프로젝트를 디버깅할 때** 확인란은 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ccd-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="34ccd-105">동일한 솔루션의 다른 프로젝트를 디버깅할 때이 특정 프로젝트에 대 한 WCF 서비스 호스트가 시작 되지 않도록 상자를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ccd-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="34ccd-106">이 동작은 F5 키를 사용한 디버깅이나 이 프로젝트의 서비스 참조 추가 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34ccd-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="34ccd-107">이 옵션은 다음 프로젝트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ccd-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="34ccd-108">WCF 서비스 라이브러리 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="34ccd-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="34ccd-109">순차 워크플로 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="34ccd-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="34ccd-110">상태 시스템 워크플로 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="34ccd-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="34ccd-111">배포 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="34ccd-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ccd-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34ccd-112">See Also</span></span>  
 [<span data-ttu-id="34ccd-113">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="34ccd-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
