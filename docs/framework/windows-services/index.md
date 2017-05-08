---
title: "Developing Windows Service Applications | Microsoft Docs"
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
  - "ServiceInstaller class, Windows Service applications"
  - "Service class, Windows Service applications"
  - "Windows Service applications"
  - "Windows NT services"
  - "ServiceProcessInstaller class, Windows Service applications"
  - "services"
  - ".NET applications, Windows applications"
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: 18
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 18
---
# Developing Windows Service Applications
Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK를 사용하면 서비스로 설치되는 응용 프로그램을 만드는 방식으로 손쉽게 서비스를 만들 수 있습니다.  이러한 응용 프로그램 종류를 Windows 서비스라고 합니다.  프레임워크 기능을 사용하여 서비스를 만들고, 설치하고, 서비스의 동작을 시작하거나 중지하고, 제어할 수도 있습니다.  
  
> [!WARNING]
>  Windows 서비스 템플릿 C\+\+ Visual Studio 2010에 포함 되지 않았습니다.  Windows 서비스를 만들려면 서비스에서 관리 되는 코드에 필요한 경우 기존 C\+\+ 코드와 상호 작용할 수, Visual Basic, 또는 C\#를 만들 수 있습니다 또는 네이티브 C\+\+를 사용 하 여 Windows 서비스를 만들 수 있는 [ATL 프로젝트 마법사](../Topic/ATL%20Project%20Wizard.md).  
  
## 단원 내용  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 수명 서비스, 및 다른 공용 프로젝트 형식과 서비스 응용 프로그램을 어떻게 Windows 서비스 응용 프로그램의 개요를 제공 합니다.  
  
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]과 Visual C\#에서 서비스를 만드는 예제를 제공합니다.  
  
 [서비스 응용 프로그램 프로그래밍 아키텍처](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 서비스 프로그래밍에 사용되는 언어 요소를 설명합니다.  
  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 만들고 Windows 서비스 프로젝트 템플릿을 사용 하 여 Windows 서비스를 구성 하는 프로세스를 설명 합니다.  
  
## 관련 단원  
 <xref:System.ServiceProcess.ServiceBase>  
 서비스를 만드는 데 사용하는 <xref:System.ServiceProcess.ServiceBase> 클래스의 주요 기능에 대해 설명합니다.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 서비스를 설치하고 제거하는 데 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용하는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스의 기능에 대해 설명합니다.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 서비스를 설치하고 제거하는 데 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용하는 <xref:System.ServiceProcess.ServiceInstaller> 클래스의 기능에 대해 설명합니다.  
  
 [템플릿에서 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 이 장에서 사용되는 프로젝트 형식과 프로젝트를 선택하는 방법에 대해 설명합니다.