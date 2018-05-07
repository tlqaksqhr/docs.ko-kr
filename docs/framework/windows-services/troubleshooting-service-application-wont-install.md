---
title: '문제 해결: 응용 프로그램 성공 서비스&#39;t 설치'
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-service-application-won39t-install"></a>문제 해결: 응용 프로그램 성공 서비스&#39;t 설치
서비스 응용 프로그램이 제대로 설치 되지 않을 경우 확인 되도록 하는 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 해당 서비스에 대 한 설치 관리자에 표시 된 대로 서비스 클래스의 속성을 같은 값으로 설정 되어 있습니다. 값 올바르게 설치 하기 위해 서비스에 대 한 순서 대로 두 인스턴스 모두에 동일 해야 합니다.  
  
> [!NOTE]
>  설치 프로세스에 피드백을 받을 설치 로그를 살펴볼 수도 있습니다.  
  
 이미 설치 된 동일한 이름의 다른 서비스를 갖고 있는지 확인 해야 합니다. 서비스 이름은 설치에 성공 하려면 고유 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
