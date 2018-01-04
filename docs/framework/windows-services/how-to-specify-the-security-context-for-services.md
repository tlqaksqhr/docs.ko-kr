---
title: "방법: 서비스에 대한 보안 컨텍스트 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 9ce65358f6d63414dbe6798d3cc2464ee2741980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a>방법: 서비스에 대한 보안 컨텍스트 지정
기본적으로 서비스에 로그인 한 사용자의 다른 보안 컨텍스트에서 실행 됩니다. 기본 시스템 계정의 컨텍스트에서 실행 되는 서비스 호출 `LocalSystem`는 서로 다른 액세스 권한을 부여 시스템 리소스에는 사용자입니다. 서비스 실행 해야 하는 다른 사용자 계정을 지정 하려면이 동작을 변경할 수 있습니다.  
  
 조작 하 여 보안 컨텍스트를 설정한는 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 서비스가 실행 되는 프로세스에 대 한 속성입니다. 이 속성을 사용 하면 서비스 네 가지 계정 형식 중 하나로 설정할 수 있습니다.  
  
-   `User`이 경우 서비스 설치 하는 네트워크에서 단일 사용자가 지정한 계정의 컨텍스트에서 실행 될 때 유효한 사용자 이름 및 암호에 대 한 메시지를 표시 하려면  
  
-   `LocalService`를 로컬 컴퓨터에서 권한 없는 사용자의 역할을 하 고; 원격 서버에 익명 자격 증명을 제공 하는 계정의 컨텍스트에서 실행 되는  
  
-   `LocalSystem`광범위 한 로컬 권한을 제공 하 고 원격 서버로; 컴퓨터의 자격 증명을 제공 하는 계정의 컨텍스트에서 실행 되는  
  
-   `NetworkService`를 로컬 컴퓨터에서 권한 없는 사용자의 역할을 원격 서버에 컴퓨터의 자격 증명을 제공 하는 계정의 컨텍스트에서 실행 됩니다.  
  
 자세한 내용은 <xref:System.ServiceProcess.ServiceAccount> 열거형을 참조하세요.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>서비스에 대 한 보안 컨텍스트를 지정 하려면  
  
1.  서비스를 만든 후에 필요한 설치 관리자를 추가 합니다. 자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.  
  
2.  디자이너에서 액세스는 `ProjectInstaller` 클래스 하 고 사용 하는 서비스에 대 한 서비스 프로세스 설치 관리자를 클릭 합니다.  
  
    > [!NOTE]
    >  모든 서비스 응용 프로그램에 대 한는에서 두 개 이상 설치 구성 요소는 `ProjectInstaller` 클래스-모든 서비스에 대 한 프로세스는 프로젝트 및 응용 프로그램을 포함 하는 각 서비스에 대해 한 명의 설치 관리자에서 설치 되도록 합니다. 이 경우에 선택 하려는 <xref:System.ServiceProcess.ServiceProcessInstaller>합니다.  
  
3.  에 **속성** 창에서 설정 된 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 적절 한 값으로.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)
