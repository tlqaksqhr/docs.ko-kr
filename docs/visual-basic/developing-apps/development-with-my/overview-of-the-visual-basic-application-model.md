---
title: Visual Basic 응용 프로그램 모델 개요
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74a8fcfe3f49ab042b3bb4775f9f6e84374db0ae
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="overview-of-the-visual-basic-application-model"></a>Visual Basic 응용 프로그램 모델 개요
Windows Forms 응용 프로그램의 동작을 제어 하기 위한 잘 정의 된 모델을 제공 하는 Visual Basic: Visual Basic 응용 프로그램 모델입니다. 이 모델에는 검색 처리 되지 않은 예외에 대 한 이벤트 뿐만 아니라 응용 프로그램의 시작 및 종료를 처리 하기 위한 이벤트가 포함 됩니다. 단일 인스턴스 응용 프로그램 개발에 대 한 지원 기능을 제공 합니다. 응용 프로그램 모델을 확장할 수 이므로 더 많은 제어가 필요한 개발자는 재정의 가능한 메서드를 사용자 지정할 수 있습니다.  
  
## <a name="uses-for-the-application-model"></a>응용 프로그램 모델에 대 한 사용  
 일반적인 응용 프로그램은 시작 하 고 종료 하는 경우 작업을 수행 해야 합니다. 예를 들어를 시작할 때 응용 프로그램 수 시작 화면을 표시, 데이터베이스 연결을 만들, 저장 된 상태 로드 등에입니다. 응용 프로그램을 종료 하는 경우 데이터베이스 연결을 닫을 현재 상태를 저장 및 등 수 것입니다. 또한 통해 응용 프로그램이 종료 될 때 특정 코드를 실행할 수 아래로 예기치 않게 같은 처리 되지 않은 예외가 발생 한 경우 처럼 합니다.  
  
 Visual Basic 응용 프로그램 모델을 사용 하면 쉽게 만들 수는 *단일 인스턴스* 응용 프로그램입니다. 단일 인스턴스 응용 프로그램을 일반 응용 프로그램에서 응용 프로그램의 인스턴스 하나만 실행할 수 있습니다 한 번에 차이가 있습니다. 단일 인스턴스 응용 프로그램의 다른 인스턴스를 시작 하려고 알리지 원래 인스턴스에서 결과-방법으로 `StartupNextInstance` 이벤트-다른 실행이 시도 했습니다. 알림을 후속 인스턴스의 명령줄 인수를 포함합니다. 응용 프로그램의 후속 인스턴스가 초기화가 실행 되기 전에 닫힙니다.  
  
 단일 인스턴스 응용 프로그램 시작 되며 첫 번째 인스턴스 또는 응용 프로그램의 후속 인스턴스에 인지 여부를 확인 합니다.  
  
-   첫 번째 인스턴스인 경우 일반적으로 시작 합니다.  
  
-   첫 번째 인스턴스가 실행 되는 동안 응용 프로그램을 시작 하려고 할 때마다 매우 다른 동작이 발생 합니다. 후속 시도 명령줄 인수에 대 한 첫 번째 인스턴스에 알립니다 하 고 즉시 종료 됩니다. 첫 번째 인스턴스 핸들은 `StartupNextInstance` 후속 인스턴스의 명령줄 인수를 및 계속 실행을 결정 하는 이벤트입니다.  
  
     이 다이어그램에서는 후속 인스턴스가 신호를 첫 번째 인스턴스가 방법을 보여 줍니다.  
  
     ![단일 인스턴스 응용 프로그램 이미지](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 처리 하 여는 `StartupNextInstance` 이벤트를 단일 인스턴스 응용 프로그램의 동작을 제어할 수 있습니다. 예를 들어, Microsoft Outlook는 일반적으로 실행; 단일 인스턴스 응용 프로그램으로 또한 문제가 계속 되 고 Outlook을 시작 하려고 할 때 원래 인스턴스에 포커스가 이동 하지만 다른 인스턴스에서 열리지 않습니다.  
  
## <a name="events-in-the-application-model"></a>응용 프로그램 모델의 이벤트  
 다음 이벤트를 응용 프로그램 모델에 있습니다.  
  
-   **응용 프로그램 시작**합니다. 발생 된 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 시작 될 때 이벤트입니다. 이 이벤트를 처리 하 여 기본 폼을 로드 하기 전에 응용 프로그램을 초기화 하는 코드를 추가할 수 있습니다. `Startup` 이벤트 시작 프로세스의 단계에 해당 하는 동안 응용 프로그램의 실행을 취소할 원하는 경우도 제공 합니다.  
  
     응용 프로그램 시작 코드를 실행 하는 동안 시작 화면을 표시 하도록 응용 프로그램을 구성할 수 있습니다. 기본적으로 응용 프로그램 모델의 시작을 억제 때 화면 중 하나는 `/nosplash` 또는 `-nosplash` 명령줄 인수를 사용 합니다.  
  
-   **단일 인스턴스 응용 프로그램**합니다. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 단일 인스턴스 응용 프로그램의 후속 인스턴스가 시작 될 때 이벤트가 발생 합니다. 이벤트의 후속 인스턴스가 명령줄 인수를 전달합니다.  
  
-   **처리 되지 않은 예외**합니다. 응용 프로그램에서 처리 되지 않은 예외를 발생 하는 경우 발생는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트입니다. 해당 이벤트의 처리기는 예외를 검사 하 고 실행을 계속할 것인지 결정 수 있습니다.  
  
     `UnhandledException` 일부 환경에서 이벤트가 발생 하지 않습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>을 참조하세요.  
  
-   **네트워크 연결 변경**합니다. 응용 프로그램에서 발생 컴퓨터의 네트워크 가용성 변경 되는 경우는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> 이벤트입니다.  
  
     `NetworkAvailabilityChanged` 일부 환경에서 이벤트가 발생 하지 않습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>을 참조하세요.  
  
-   **응용 프로그램이 종료**합니다. 응용 프로그램이 제공 된 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 종료 하려고 하는 경우 신호를 보내는 이벤트입니다. 해당 이벤트에 처리기를 할 수 있습니다 하는 작업 응용 프로그램을 수행 해야-닫기 및 예를 들어 저장-완료 됩니다. 기본 폼이 닫힐 때 종료 되거나 모든 폼이 닫힐 때만 종료 하려면 응용 프로그램을 구성할 수 있습니다.  
  
## <a name="availability"></a>가용성  
 기본적으로 Visual Basic 응용 프로그램 모델은 Windows Forms 프로젝트에 사용할 수 있습니다. 서로 다른 여러 시작 개체를 사용 하도록 응용 프로그램을 구성 하는 경우 또는 응용 프로그램 코드를 사용자 지정 시작 `Sub Main`, 하는 개체 또는 클래스의 구현을 제공 해야 할 수는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 응용 프로그램 모델을 사용 하는 클래스입니다. 시작 개체 변경 하는 방법에 대 한 정보를 참조 하십시오. [응용 프로그램 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Visual Basic 응용 프로그램 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
