---
title: WCF 서비스 호스트 자동 시작 제어
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: fe936ee3ff42b586c733de597de808b86f3e2575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>WCF 서비스 호스트 자동 시작 제어
에 대 한 Windows Communication Foundation (WCF) 서비스 호스트 (WcfSvcHost.exe)의 자동 시작 기능을 제어할 수 있습니다는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트에 여러 프로젝트가 포함 된 같은 Visual Studio 솔루션의 다른 프로젝트를 디버그할 때 .  
  
 이렇게 하려면 마우스 오른쪽 단추로 클릭는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트에 **솔루션 탐색기**, 선택 **속성**를 클릭 하 고 **WCF 옵션** 탭 합니다. **WCF 서비스 호스트 시작 동일한 솔루션의 다른 프로젝트를 디버깅할 때** 확인란은 기본적으로 사용 됩니다. 같은 솔루션의 다른 프로젝트를 디버깅할 때 이 특정 프로젝트에 대해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 시작되지 않게 하려면 이 확인란의 선택을 취소할 수 있습니다.  
  
 이 동작은 F5 키를 사용한 디버깅이나 이 프로젝트의 서비스 참조 추가 기능에는 영향을 주지 않습니다.  
  
 이 옵션은 다음 프로젝트에 사용할 수 있습니다.  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트  
  
-   순차 워크플로 서비스 라이브러리 프로젝트  
  
-   상태 시스템 워크플로 서비스 라이브러리 프로젝트  
  
-   배포 서비스 라이브러리 프로젝트  
  
## <a name="see-also"></a>참고 항목  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
