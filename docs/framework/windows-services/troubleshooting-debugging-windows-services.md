---
title: '문제 해결: Windows 서비스 디버깅'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
manager: douge
ms.openlocfilehash: 77a0c19c2da2d1886beaf396650fa024fc1243a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-debugging-windows-services"></a>문제 해결: Windows 서비스 디버깅
Windows 서비스 응용 프로그램, 서비스를 디버그할 때 및 **Windows 서비스 관리자** 상호 작용 합니다. **Service Manager** 호출 하 여 서비스를 시작한는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 30 초 정도 대기는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 반환 합니다. 이 메서드가 반환 하지 않으면, 관리자는 오류를 보여 줍니다 서비스를 시작할 수 없습니다.  
  
 디버그할 때는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드에 설명 된 대로 [하는 방법: Windows 서비스 응용 프로그램 디버그](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), 30 초 그러는 알고 있어야 합니다. 중단점을 배치 하는 경우는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드 30 초 내에 것 단계별로 실행 하지 않는 하 고, 관리자 서비스를 시작 하지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows 서비스 응용 프로그램 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
