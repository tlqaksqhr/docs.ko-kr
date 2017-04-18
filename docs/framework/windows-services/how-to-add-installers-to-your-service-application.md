---
title: "방법: 서비스 응용 프로그램에 설치 관리자 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "설치 구성 요소, 서비스에 추가"
  - "설치 관리자, 서비스에 추가"
  - "ServiceInstaller 클래스, 서비스에 설치 관리자 추가"
  - "ServiceProcessInstaller 클래스, 서비스에 설치 관리자 추가"
  - "서비스, 설치 관리자 추가"
  - "Windows 서비스 응용 프로그램, 설치 관리자 추가"
  - "Windows 서비스 응용 프로그램, 배포"
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# 방법: 서비스 응용 프로그램에 설치 관리자 추가
Visual Studio는 서비스 응용 프로그램과 관련된 리소스를 설치할 수 있는 설치 구성 요소를 제공합니다.  설치 구성 요소는 개별 서비스를 설치할 시스템에 이 서비스를 등록하여 서비스 제어 관리자에게 서비스가 있음을 알려 줍니다.  서비스 응용 프로그램을 사용할 때 속성 창의 링크를 선택하면 프로젝트에 해당하는 설치 관리자를 자동으로 추가할 수 있습니다.  
  
> [!NOTE]
>  서비스에 대한 속성 값은 서비스 클래스에서 설치 관리자 클래스로 복사됩니다.  서비스 클래스의 속성 값을 업데이트하더라도 설치 관리자의 속성 값은 자동으로 업데이트되지 않습니다.  
  
 프로젝트에 설치 관리자를 추가할 때 기본적으로 `ProjectInstaller`로 명명되는 새 클래스가 프로젝트에 만들어지고 적절한 설치 구성 요소 인스턴스가 클래스에 만들어집니다.  이 클래스는 프로젝트에 필요한 모든 설치 구성 요소의 중심점 역할을 합니다.  예를 들어, 응용 프로그램에 두 번째 서비스를 추가하고 설치 관리자 추가 링크를 클릭하면 두 번째 설치 관리자 클래스가 만들어지지 않고 기존 클래스에 두 번째 서비스에 필요한 추가 설치 구성 요소가 추가됩니다.  
  
 서비스를 제대로 설치하기 위해 설치 관리자 내에 별도의 코드를 작성할 필요는 없습니다.  그러나 설치 프로세스에 특별한 기능을 추가하려면 경우에 따라 설치 관리자의 내용을 수정해야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 서비스 응용 프로그램에 설치 관리자를 추가하려면  
  
1.  **솔루션 탐색기**에서 설치 구성 요소를 추가할 서비스에 대한 **디자인** 뷰에 액세스합니다.  
  
2.  디자이너의 배경을 클릭하여 서비스 내용이 아닌 서비스 자체를 선택합니다.  
  
3.  디자이너에 포커스가 있는 상태에서 **설치 관리자 추가**를 클릭합니다.  
  
     새로운 클래스 `ProjectInstaller`와 두 설치 구성 요소인 <xref:System.ServiceProcess.ServiceProcessInstaller> 및 <xref:System.ServiceProcess.ServiceInstaller>가 프로젝트에 추가되고 서비스에 대한 속성 값이 구성 요소에 복사됩니다.  
  
4.  <xref:System.ServiceProcess.ServiceInstaller> 구성 요소를 클릭하여 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성의 값이 서비스 자체의 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성 값과 동일하게 설정되었는지 확인합니다.  
  
5.  서비스 시작 방법을 결정하려면 <xref:System.ServiceProcess.ServiceInstaller> 구성 요소를 클릭한 다음 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|결과|  
    |-------|--------|  
    |<xref:System.ServiceProcess.ServiceStartMode>|설치 후 수동으로 서비스를 시작해야 합니다.  자세한 내용은 [방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)을 참조하십시오.|  
    |<xref:System.ServiceProcess.ServiceStartMode>|컴퓨터를 다시 부팅할 때마다 서비스가 자동으로 시작됩니다.|  
    |<xref:System.ServiceProcess.ServiceStartMode>|서비스를 시작할 수 없습니다.|  
  
6.  서비스가 실행되는 보안 컨텍스트를 결정하려면 <xref:System.ServiceProcess.ServiceProcessInstaller> 구성 요소를 클릭하여 적절한 속성 값을 설정합니다.  자세한 내용은 [방법: 서비스에 대한 보안 컨텍스트 지정](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)을 참조하십시오.  
  
7.  사용자 지정 처리를 수행해야 하는 모든 메서드를 재정의합니다.  
  
8.  프로젝트의 각 추가 서비스에 대해 1단계부터 7단계까지 수행합니다.  
  
    > [!NOTE]
    >  프로젝트에 있는 각 추가 서비스에 대해 프로젝트의 `ProjectInstaller` 클래스에 추가 <xref:System.ServiceProcess.ServiceInstaller> 구성 요소를 추가해야 합니다.  3단계에서 추가된 <xref:System.ServiceProcess.ServiceProcessInstaller> 구성 요소는 프로젝트에서의 모든 개별 서비스 설치 관리자를 사용합니다.  
  
## 참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [방법: 서비스 설치 및 제거](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)   
 [방법: 서비스에 대한 보안 컨텍스트 지정](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)