---
title: Windows 컨테이너를 배포 하지 않는 경우
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | Windows 컨테이너를 배포 하지 않는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 819f32955ff019414bef8820d17d272eddc11bf8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957963"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="533e4-103">Windows 컨테이너를 배포 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="533e4-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="533e4-104">일부 Windows 기술은 Windows 컨테이너에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="533e4-105">이 경우 여전히 창과 IIS와 일반적으로 표준 Vm에 마이그레이션해야 할.</span><span class="sxs-lookup"><span data-stu-id="533e4-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="533e4-106">사례 2018 년 5 월부터 Windows 컨테이너에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="533e4-107">현재 Microsoft 메시지 큐 (MSMQ)은 다른 이전 릴리스의 있지만 Windows Server v1803 릴리스를 기준으로 하는 Windows 컨테이너에 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="533e4-108">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="533e4-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="533e4-109">토론 포럼</span><span class="sxs-lookup"><span data-stu-id="533e4-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="533e4-110">Microsoft Distributed Transaction Coordinator (MSDTC) 현재 지원 되지 않습니다 Windows 컨테이너에서.</span><span class="sxs-lookup"><span data-stu-id="533e4-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="533e4-111">GitHub 문제</span><span class="sxs-lookup"><span data-stu-id="533e4-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="533e4-112">현재 Microsoft Office 컨테이너를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="533e4-113">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="533e4-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="533e4-114">UI 응용 프로그램 (시각적 사용자 인터페이스와 클라이언트의 응용 프로그램) 지원 되는 시나리오 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="533e4-115">Windows 인프라 역할 (DNS, DHCP, DC, NTP, 인쇄, 파일 서버, IAM 등) 하지 시나리오는 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="533e4-116">Windows 컨테이너에 대 한 추가 지원 되지 않는 시나리오 및 커뮤니티에서 요청에 대 한 UserVoice 포럼을 참조: <https://windowsserver.uservoice.com/forums/304624-containers>합니다.</span><span class="sxs-lookup"><span data-stu-id="533e4-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="533e4-117">추가 자료</span><span class="sxs-lookup"><span data-stu-id="533e4-117">Additional resources</span></span>

-   <span data-ttu-id="533e4-118">**가상 컴퓨터와 Azure의 컨테이너**</span><span class="sxs-lookup"><span data-stu-id="533e4-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="533e4-119">[이전](deploy-existing-net-apps-as-windows-containers.md)
[다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="533e4-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
