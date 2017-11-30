---
title: "Windows 컨테이너를 배포 하지 않는 경우"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Windows 컨테이너를 배포 하지 않는 경우"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Windows 컨테이너를 배포 하지 않는 경우

일부 Windows 기술은 Windows 컨테이너에서 지원 되지 않습니다. 이 경우 여전히 창과 IIS와 일반적으로 표준 Vm에 마이그레이션해야 할.

사례 2017 중순 현재 Windows 컨테이너에서 지원 되지 않습니다.

-   Microsoft 메시지 큐 (MSMQ) 현재 지원 되지 않습니다 Windows 컨테이너에서.

    -   [UserVoice 요청 포럼](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [토론 포럼](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator (MSDTC) 현재 Windows 컨테이너에서 지원 되지 않습니다.

    -   [GitHub 문제](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office 컨테이너를 현재 지원 하지 않습니다.

    -   [UserVoice 요청 포럼](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

Windows 컨테이너에 대 한 추가 지원 되지 않는 시나리오 및 커뮤니티에서 요청에 대 한 UserVoice 포럼을 참조: <https://windowsserver.uservoice.com/forums/304624-containers>합니다.

### <a name="additional-resources"></a>추가 리소스

-   **가상 컴퓨터와 Azure의 컨테이너**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[이전](deploy-existing-net-apps-as-windows-containers.md)
[다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
