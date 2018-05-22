---
title: Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치
description: Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5를 설치하는 방법을 알아봅니다.
author: rlander
ms.author: mairaw
ms.date: 03/30/2018
ms.openlocfilehash: 226449b8ee7c9360e6bfdc5bfa5dfeb59f19bd2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치

Windows 10, Windows 8.1 및 Windows 8에서 앱을 실행하려면 .NET Framework 3.5가 필요할 수 있습니다. 이러한 지침은 이전 Windows 버전에도 사용할 수 있습니다.

## <a name="install-the-net-framework-35-on-demand"></a>요청 시 .NET Framework 3.5 설치

.NET Framework 3.5가 필요한 앱을 실행하려고 하면 다음 구성 대화 상자가 표시될 수 있습니다. **이 기능 설치**를 선택하여 .NET Framework 3.5를 사용하도록 설정합니다. 이 옵션을 사용하려면 인터넷에 연결해야 합니다.

![.NET Framework 설치 대화 상자](./media/dotnet-framework-installation-dialog.jpg)

### <a name="why-am-i-getting-this-pop-up"></a>이 팝업이 표시되는 이유는 무엇인가요?

.NET Framework는 Microsoft에서 만들어지고 응용 프로그램을 실행하기 위한 환경을 제공합니다. 사용 가능한 다양한 버전이 있습니다. 많은 회사에서 .NET Framework를 사용하여 실행할 앱을 개발하고 이러한 앱은 특정 버전을 대상으로 합니다. 이 팝업이 표시되면 .NET Framework 버전 3.5가 필요한 응용 프로그램을 실행하려고 하지만 해당 버전이 시스템에 설치되어 있지 않은 것입니다.

## <a name="enable-the-net-framework-35-in-control-panel"></a>제어판에서 .NET Framework 3.5를 사용하도록 설정

Windows 제어판을 통해 .NET Framework 3.5를 사용하도록 설정할 수 있습니다. 이 옵션을 사용하려면 인터넷에 연결해야 합니다.

1. 키보드에서 Windows 키 ![Windows 로고](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg)를 누르고, “Windows 기능”을 입력한 후 Enter 키를 누릅니다. **Windows 기능 사용/사용 안 함** 대화 상자가 나타납니다.

2. **.NET Framework 3.5(.NET 2.0 및 3.0 포함)** 확인란을 선택하고, **확인**을 선택하고, 메시지가 표시되면 컴퓨터를 다시 부팅합니다.

   ![제어판으로 .NET 설치](./media/dotnet-control-panel.png)

   이 기능이 필요한 개발자 또는 서버 관리자가 아니라면 **WCF(Windows Communication Foundation) HTTP 활성화** 및 **WCF(Windows Communication Foundation) 비 HTTP 활성화**를 위한 자식 항목을 선택할 필요가 없습니다.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>.NET Framework 3.5 설치 문제 해결

설치 중 0x800f0906, 0x800f0907, 0x800f081f 또는 0x800F0922 오류가 발생할 수 있습니다. 이 경우 [.NET Framework 3.5 설치 오류: 0x800f0906, 0x800f0907 또는 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09)를 참조하여 이러한 문제 해결 방법을 확인하세요.

여전히 설치 문제를 해결할 수 없거나 인터넷에 연결되어 있지 않으면 Windows 설치 미디어를 사용하여 설치를 시도할 수 있습니다. 자세한 내용은 [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism)(DISM(배포 이미지 서비스 및 관리)을 사용하여 .NET Framework 3.5 배포)를 참조하세요. 설치 미디어가 없는 경우 [Windows용 설치 미디어 만들기](https://support.microsoft.com/help/15088/windows-create-installation-media)를 참조하세요.
