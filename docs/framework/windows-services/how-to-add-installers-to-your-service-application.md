---
title: "방법: 서비스 응용 프로그램에 설치 관리자 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 15487d4311f896aa09c1c7712292058086a49b50
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-installers-to-your-service-application"></a>방법: 서비스 응용 프로그램에 설치 관리자 추가
Visual Studio 리소스에 연결 된 서비스 응용 프로그램을 설치할 수 있는 설치 구성 요소를 제공 합니다. 설치 구성 요소는 시스템을 설치 하는 것와를 서비스가 존재 하는지 확인 하 여 서비스 제어 관리자에서 개별 서비스를 등록 합니다. 서비스 응용 프로그램을 사용할 때 자동으로 프로젝트에 적절 한 설치 관리자를 추가 하려면 속성 창에서 링크를 선택할 수 있습니다.  
  
> [!NOTE]
>  서비스에 대 한 속성 값은 설치 관리자 클래스에는 서비스 클래스에서 복사 됩니다. 서비스 클래스에서 속성 값을 업데이트 하는 경우 설치 관리자에서 자동으로 업데이트 되는 것은 되지 합니다.  
  
 프로젝트는 새 클래스에는 설치 관리자를 추가 하면 (, 기본적으로 라는 `ProjectInstaller`) 프로젝트 및 구성 요소에 만들어집니다. 해당 설치의 인스턴스가 만들어집니다. 프로젝트에 필요한이 클래스 역할의 모든 설치 구성 요소에 대 한 중심점. 예를 들어 두 번째 서비스 응용 프로그램에 추가 하 고 설치 관리자 추가 링크를 클릭 하는 경우 두 번째 설치 관리자 클래스 만들어지지 않습니다. 대신, 두 번째 서비스에 대 한 필요한 추가 설치 구성 요소는 기존 클래스에 추가 됩니다.  
  
 서비스를 제대로 설치 되도록 설치 관리자 내에서 특별 한 코딩이 할 필요가 없습니다. 그러나 설치 프로세스에 특별 한 기능을 추가 해야 할 경우 설치 관리자의 내용을 수정 해야 경우에 따라 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-installers-to-your-service-application"></a>서비스 응용 프로그램에 설치 관리자를 추가 하려면  
  
1.  **솔루션 탐색기**, 액세스 **디자인** 설치 구성 요소를 추가 하려는 서비스에 대 한 보기입니다.  
  
2.  자체 보다는 내용이 서비스를 선택 하려면 디자이너의 배경을 클릭 합니다.  
  
3.  포커스 마우스 오른쪽 단추로 클릭 한 다음 디자이너와 **설치 관리자 추가**합니다.  
  
     새 클래스를 `ProjectInstaller`, 두 가지 설치 구성 요소 및 <xref:System.ServiceProcess.ServiceProcessInstaller> 및 <xref:System.ServiceProcess.ServiceInstaller>, 구성 요소에 복사 되는 서비스에 대 한 프로젝트 및 속성 값에 추가 됩니다.  
  
4.  클릭는 <xref:System.ServiceProcess.ServiceInstaller> 구성 요소 확인 값은 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성이 동일한 값으로 설정 되어는 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 서비스 자체의 속성입니다.  
  
5.  서비스는 시작 하는 방법을 확인 하려면는 <xref:System.ServiceProcess.ServiceInstaller> 설정 및 구성 요소는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 적절 한 값입니다.  
  
    |값|결과|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|설치 후 서비스를 수동으로 시작 해야 합니다. 자세한 내용은 참조 [하는 방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)합니다.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|서비스는 컴퓨터가 재부팅 될 때마다 자동으로 시작 됩니다.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|서비스를 시작할 수 없습니다.|  
  
6.  프로그램 서비스가 실행 되는 보안 컨텍스트를 확인 하려면 클릭는 <xref:System.ServiceProcess.ServiceProcessInstaller> 구성 요소 및 해당 속성 값을 설정 합니다. 자세한 내용은 참조 [하는 방법: 서비스에 대 한 보안 컨텍스트 지정](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)합니다.  
  
7.  사용자 지정 처리를 수행 해야 하는 메서드를 재정의 합니다.  
  
8.  프로젝트의 각 추가 서비스에 대해 1-7 단계를 수행 합니다.  
  
    > [!NOTE]
    >  프로젝트의 각 추가 서비스를 추가 해야 추가 <xref:System.ServiceProcess.ServiceInstaller> 프로젝트의 구성 요소 `ProjectInstaller` 클래스입니다. <xref:System.ServiceProcess.ServiceProcessInstaller> 모든 프로젝트에 있는 개별 서비스 설치 관리자와 3 단계에서 추가 하는 구성 요소의 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [방법: 서비스 설치 및 제거](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)  
 [방법: 서비스에 대한 보안 컨텍스트 지정](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
