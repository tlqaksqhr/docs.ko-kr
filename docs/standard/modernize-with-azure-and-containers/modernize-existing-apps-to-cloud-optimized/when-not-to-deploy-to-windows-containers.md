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
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Windows 컨테이너를 배포 하지 않는 경우

일부 Windows 기술은 Windows 컨테이너에서 지원 되지 않습니다. 이 경우 여전히 창과 IIS와 일반적으로 표준 Vm에 마이그레이션해야 할.

사례 2018 년 5 월부터 Windows 컨테이너에서 지원 되지 않습니다. 

-   현재 Microsoft 메시지 큐 (MSMQ)은 다른 이전 릴리스의 있지만 Windows Server v1803 릴리스를 기준으로 하는 Windows 컨테이너에 사용할 수만 있습니다. 

    -   [UserVoice 요청 포럼](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [토론 포럼](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator (MSDTC) 현재 지원 되지 않습니다 Windows 컨테이너에서.

    -   [GitHub 문제](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   현재 Microsoft Office 컨테이너를 지원 하지 않습니다.

    -   [UserVoice 요청 포럼](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   UI 응용 프로그램 (시각적 사용자 인터페이스와 클라이언트의 응용 프로그램) 지원 되는 시나리오 않습니다.

-   Windows 인프라 역할 (DNS, DHCP, DC, NTP, 인쇄, 파일 서버, IAM 등) 하지 시나리오는 지원 합니다.


Windows 컨테이너에 대 한 추가 지원 되지 않는 시나리오 및 커뮤니티에서 요청에 대 한 UserVoice 포럼을 참조: <https://windowsserver.uservoice.com/forums/304624-containers>합니다.

### <a name="additional-resources"></a>추가 자료

-   **가상 컴퓨터와 Azure의 컨테이너**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[이전](deploy-existing-net-apps-as-windows-containers.md)
[다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
