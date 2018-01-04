---
title: "Windows 서비스 응용 프로그램 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 17d4c5908929f02077b1eb48932a50e83f48d076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="developing-windows-service-applications"></a>Windows 서비스 응용 프로그램 개발
Microsoft를 사용 하 여 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK를 쉽게 만들 수 있습니다 서비스 서비스로 설치 하는 응용 프로그램을 만들어 합니다. 이 유형의 응용 프로그램에는 Windows 서비스를 라고 합니다. Framework 기능을 사용 있습니다 수는 서비스를 만들, 설치, 시작, 중지 및 그렇지 않은 경우의 동작을 제어 합니다.  
  
> [!WARNING]
>  C + +에 대 한 Windows 서비스 템플릿은 Visual Studio 2010에 포함 되지 않았습니다. Windows 서비스를 만들려면 Visual C# 또는 Visual Basic, 필요한 경우 기존 c + + 코드 상호 작용할 수에서 관리 코드에서 서비스를 만들 수 있습니다 또는 네이티브 c + +에서를 사용 하 여 Windows 서비스를 만들 수는 [ATL프로젝트마법사](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>섹션 내용  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 서비스 및 서비스 응용 프로그램 다른 공통 프로젝트 형식에서 어떻게 다른 지의 수명을 Windows 서비스 응용 프로그램에 대 한 개요를 제공 합니다.  
  
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 서비스를 만드는 예제를 제공 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 및 Visual C#입니다.  
  
 [서비스 응용 프로그램 프로그래밍 아키텍처](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 서비스 프로그래밍에 사용 되는 언어 요소에 설명 합니다.  
  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 만들기 및 Windows 서비스 프로젝트 템플릿을 사용 하 여 Windows 서비스를 구성 하는 과정을 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 <xref:System.ServiceProcess.ServiceBase>  
 주요 기능에 설명 된 <xref:System.ServiceProcess.ServiceBase> 서비스를 만드는 데 사용 되는 클래스입니다.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 기능을 설명는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용 하는 <xref:System.ServiceProcess.ServiceInstaller> 클래스 설치 하 고 서비스를 제거 합니다.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 기능을 설명는 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용 하는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스 설치 하 고 서비스를 제거 합니다.  
  
 [NIB 템플릿에서 프로젝트 만들기](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 프로젝트 선택 하는 방법과이 장의에 사용 되는 형식입니다.
