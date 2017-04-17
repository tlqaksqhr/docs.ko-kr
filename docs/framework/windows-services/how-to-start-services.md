---
title: "방법: 서비스 시작 | Microsoft Docs"
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
  - "서비스, 시작"
  - "Windows 서비스 응용 프로그램, 시작"
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# 방법: 서비스 시작
서비스는 설치한 다음 시작해야 합니다.  서비스를 시작하면 서비스 클래스에서 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 호출합니다.  일반적으로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드는 서비스에서 수행할 유용한 작업을 정의합니다.  서비스는 시작되고 나면 수동으로 일시 중지 또는 중지할 때까지 활성화되어 있습니다.  
  
 서비스를 자동으로 시작하거나 수동으로 시작하도록 설정할 수 있습니다.  자동으로 시작하는 서비스는 서비스가 설치된 컴퓨터를 다시 부팅하거나 처음 켤 때 시작됩니다.  수동으로 시작하는 서비스는 사용자가 직접 시작해야 합니다.  
  
> [!NOTE]
>  기본적으로 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 만든 서비스는 수동으로 시작되도록 설정됩니다.  
  
 **서버 탐색기**에서, **서비스 제어 관리자**에서 또는 <xref:System.ServiceProcess.ServiceController>를 호출한 구성 요소를 사용하여 코드에서 서비스를 수동으로 시작할 수 있습니다.  
  
 서비스를 자동으로 시작할 지 수동으로 시작할 지 지정하려면 <xref:System.ServiceProcess.ServiceInstaller> 클래스에 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 설정합니다.  
  
### 서비스 시작 방법을 지정하려면  
  
1.  서비스를 만든 후 필요한 설치 관리자를 추가합니다.  자세한 내용은 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)을 참조하십시오.  
  
2.  디자이너에서 사용할 서비스에 대한 서비스 설치 관리자를 클릭합니다.  
  
3.  **속성** 창에서 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 다음 중 하나로 설정합니다.  
  
    |서비스 설치 시점|설정 값|  
    |---------------|----------|  
    |컴퓨터가 다시 시작될 때|**자동**|  
    |명시적인 사용자 동작으로 서비스를 시작할 때|**수동**|  
  
    > [!TIP]
    >  서비스의 시작을 완전히 막으려면 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 **사용 안 함**으로 설정합니다.  서버를 여러 번 다시 부팅하려는 경우와 정상적으로 시작되는 서비스를 시작하지 못하게 하여 부팅 시간을 절약하려는 경우 이렇게 설정하면 됩니다.  
  
    > [!NOTE]
    >  서비스를 설치한 후에도 여러 속성을 변경할 수 있습니다.  
  
     <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 프로세스가 **수동**로 설정된 서비스는 **서버 탐색기**에서, **Windows 서비스 제어 관리자**에서 또는 코드에서 시작할 수 있습니다.  그러나 이러한 모든 메서드가 실제로 **서비스 제어 관리자**의 컨텍스트에서 서비스를 시작하는 것이 아니라 **서버 탐색기** 및 서비스를 시작하는 프로그래밍 방식 메서드가 실제로 컨트롤러를 조작합니다.  
  
### 서버 탐색기에서 서비스를 수동으로 시작하려면  
  
1.  **서버 탐색기**의 목록에 원하는 서버가 없으면 추가합니다.  자세한 내용은 [방법: 서버 탐색기\/데이터베이스 탐색기 액세스 및 초기화](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md)을 참조하십시오.  
  
2.  **서비스** 노드를 확장한 다음 시작할 서비스를 찾습니다.  
  
3.  서비스 이름을 마우스 오른쪽 단추로 클릭한 다음 **시작**을 클릭합니다.  
  
### 서비스 제어 관리자에서 서비스를 수동으로 시작하려면  
  
1.  다음 중 한 가지 방법으로 **서비스 제어 관리자**를 엽니다.  
  
    -   Windows XP 및 2000 Professional에서 바탕 화면의 **내 컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 **관리**를 클릭합니다.  표시되는 대화 상자에서 **서비스 및 응용 프로그램** 노드를 확장합니다.  
  
         \-또는\-  
  
    -   Windows Server 2003 및 Windows 2000 Server에서는 **시작**을 클릭하고 **프로그램**을 가리킨 다음 **관리 도구**와 **서비스**를 차례로 클릭합니다.  
  
        > [!NOTE]
        >  Windows NT 4.0에서는 **제어판**에서 이 대화 상자를 열 수 있습니다.  
  
     창의 **서비스** 섹션에 서비스 목록이 표시됩니다.  
  
2.  목록에서 서비스를 선택하고 마우스 오른쪽 단추로 클릭한 다음 **시작**을 클릭합니다.  
  
### 코드에서 서비스를 수동으로 시작하려면  
  
1.  <xref:System.ServiceProcess.ServiceController> 클래스 인스턴스를 만들고 관리할 서비스와 상호 작용하도록 구성합니다.  
  
2.  <xref:System.ServiceProcess.ServiceController.Start%2A> 메서드를 호출하여 서비스를 시작합니다.  
  
## 참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [방법: 서버 탐색기\/데이터베이스 탐색기 액세스 및 초기화](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md)