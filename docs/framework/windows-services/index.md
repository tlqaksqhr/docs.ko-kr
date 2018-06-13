---
title: Windows 서비스 응용 프로그램 개발
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: af6e4bf7697b3139f6809295737fdd0d90b7f013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512270"
---
# <a name="developing-windows-service-applications"></a>Windows 서비스 응용 프로그램 개발
Microsoft Visual Studio나 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK를 사용하면 서비스로 설치되는 응용 프로그램을 만들어 서비스를 쉽게 만들 수 있습니다. 이 유형의 응용 프로그램을 Windows 서비스라고 합니다. 프레임워크 기능을 사용하여 서비스를 만들고 설치하고 시작 및 중지할 수 있으며 서비스 동작을 제어할 수도 있습니다.  
  
> [!WARNING]
>  C++용 Windows 서비스 템플릿은 Visual Studio 2010에 포함되지 않았습니다. Windows 서비스를 만들려면 Visual C#이나 Visual Basic에서 관리 코드로 서비스를 만들거나(필요한 경우 이러한 코드와 기존 C++ 코드를 함께 사용할 수 있음) 네이티브 C++에서 [ATL 프로젝트 마법사](/cpp/atl/reference/atl-project-wizard)를 사용하여 Windows 서비스를 만들 수도 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Windows 서비스 응용 프로그램, 서비스 수명 및 서비스 응용 프로그램이 다른 일반적인 프로젝트 유형과 다른 점에 대해 간략히 설명합니다.  
  
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Visual Basic 및 Visual C#에서 서비스를 만드는 예제를 제공합니다.  
  
 [서비스 응용 프로그램 프로그래밍 아키텍처](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 서비스 프로그래밍에서 사용되는 언어 요소에 대해 설명합니다.  
  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Windows 서비스 프로젝트 템플릿을 사용하여 Windows 서비스를 만들고 구성하는 프로세스에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 <xref:System.ServiceProcess.ServiceBase>  
 서비스를 만드는 데 사용되는 <xref:System.ServiceProcess.ServiceBase> 클래스의 주요 기능에 대해 설명합니다.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스의 기능에 대해 설명합니다.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceInstaller> 클래스의 기능에 대해 설명합니다.  
  
 [NIB Creating Projects from Templates](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)(NIB 템플릿에서 프로젝트 만들기)  
 이 장에서 사용되는 프로젝트 유형과 이들 유형 중에서 선택하는 방법을 설명합니다.
