---
title: "방법: 서비스에 대한 보안 컨텍스트 지정 | Microsoft Docs"
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
  - "컨텍스트, Visual Studio 보안"
  - "보안[Visual Studio], 컨텍스트"
  - "보안[Visual Studio], 서비스 응용 프로그램"
  - "ServiceInstaller 클래스, 보안 컨텍스트"
  - "ServiceProcessInstaller 클래스, 보안 컨텍스트"
  - "서비스, 보안"
  - "Windows 서비스 응용 프로그램, 보안"
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 10
---
# 방법: 서비스에 대한 보안 컨텍스트 지정
기본적으로 서비스는 로그인한 사용자와 다른 보안 컨텍스트에서 실행됩니다.  서비스는 시스템 리소스에 대해 사용자와 다른 액세스 권한을 부여하는 `LocalSystem`이라는 기본 시스템 계정의 컨텍스트에서 실행됩니다.  이 동작을 변경하여 서비스가 실행될 다른 사용자 계정을 지정할 수 있습니다.  
  
 서비스가 실행되는 프로세스의 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 속성을 조작하여 보안 컨텍스트를 설정합니다.  이 속성을 사용하면 서비스를 다음 네 가지 계정 형식 중 하나로 설정할 수 있습니다.  
  
-   `User` — 서비스를 설치할 때 유효한 사용자 이름과 암호를 입력해야 합니다. 서비스는 네트워크에서 단일 사용자가 지정한 계정의 컨텍스트에서 실행됩니다.  
  
-   `LocalService` — 서비스는 로컬 컴퓨터에 있는 권한이 없는 사용자 계정의 컨텍스트에서 실행되며 원격 서버에 익명 자격 증명을 제공합니다.  
  
-   `LocalSystem`광범위 한 로컬 권한을 제공 하 고; 원격 서버에 컴퓨터의 자격 증명을 제공 하는 계정의 컨텍스트에서 실행  
  
-   `NetworkService` — 서비스는 로컬 컴퓨터에 있는 권한이 없는 사용자 계정의 컨텍스트에서 실행되며 원격 서버에 컴퓨터의 자격 증명을 제공합니다.  
  
 자세한 내용은 <xref:System.ServiceProcess.ServiceAccount> 열거형을 참조하십시오.  
  
### 서비스에 대한 보안 컨텍스트를 지정하려면  
  
1.  서비스를 만든 후 필요한 설치 관리자를 추가합니다.  자세한 내용은 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)을 참조하십시오.  
  
2.  디자이너에서 `ProjectInstaller` 클래스에 액세스하고 사용할 서비스에 대한 프로세스 설치 관리자를 클릭합니다.  
  
    > [!NOTE]
    >  모든 서비스 응용 프로그램의 `ProjectInstaller` 클래스에는 적어도 두 개의 설치 구성 요소가 있습니다. 하나는 프로젝트의 모든 서비스에 대한 프로세스를 설치하는 요소이고 다른 하나는 응용 프로그램에 포함된 각 서비스에 대한 설치 관리자입니다.  현재 인스턴스에서는 <xref:System.ServiceProcess.ServiceProcessInstaller>를 선택합니다.  
  
3.  **속성** 창에서 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>를 적절한 값으로 설정합니다.  
  
## 참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)