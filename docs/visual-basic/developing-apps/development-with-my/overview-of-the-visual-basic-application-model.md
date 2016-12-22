---
title: "Overview of the Visual Basic Application Model | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application object, Visual Basic application model"
  - "Visual Basic application model"
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Overview of the Visual Basic Application Model
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 Windows Forms 응용 프로그램의 동작을 제어하기 위한 잘 정의된 모델인 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 응용 프로그램 모델을 제공합니다.  이 모델에는 처리되지 않은 예외를 catch하기 위한 이벤트와 응용 프로그램의 시작 및 종료를 처리하기 위한 이벤트가 포함됩니다.  또한 단일 인스턴스 응용 프로그램 개발을 위한 지원도 제공합니다.  응용 프로그램 모델은 확장이 가능하므로 더 많은 제어가 필요한 개발자는 재정의 가능한 메서드를 사용자 지정할 수 있습니다.  
  
## 응용 프로그램 모델의 용도  
 일반적인 응용 프로그램은 시작하고 종료할 때 작업을 수행해야 합니다.  예를 들어, 응응 프로그램은 시작할 때 시작 화면을 표시하고 데이터베이스 연결을 만들고 저장된 상태를 로드하는 등의 작업을 수행할 수 있습니다.  종료할 때는 데이터베이스 연결을 닫고 현재 상태를 저장하는 등의 작업을 수행할 수 있습니다.  또한 응용 프로그램은 처리되지 않은 예외가 발생한 경우처럼 예기치 않게 종료될 때 특정 코드를 실행할 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 응용 프로그램 모델을 사용하면 *단일 인스턴스* 응용 프로그램을 쉽게 만들 수 있습니다.  단일 인스턴스 응용 프로그램은 응용 프로그램 인스턴스를 한 번에 하나씩만 실행할 수 있다는 점에서 일반 응용 프로그램과 다릅니다.  단일 인스턴스 응용 프로그램에서 다른 인스턴스를 추가로 시작하려고 하면 원래 실행 중이던 인스턴스는 `StartupNextInstance` 이벤트를 통해 다른 시작이 시도되었다는 알림을 받게 됩니다.  이 알림에는 후속 인스턴스의 명령줄 인수가 포함됩니다.  그러면 응용 프로그램의 후속 인스턴스는 초기화가 실행되기 전에 닫힙니다.  
  
 단일 인스턴스 응용 프로그램은 시작될 때 자신이 응용 프로그램의 첫 번째 인스턴스인지 후속 인스턴스인지 확인합니다.  
  
-   첫 번째 인스턴스이면 정상적으로 시작됩니다.  
  
-   첫 번째 인스턴스가 실행되고 있는 동안 응용 프로그램을 시작하려는 시도가 이루어지면 그때마다 결과 동작은 매우 달라집니다.  후속 시도는 첫 번째 인스턴스에 명령줄 인수에 대해 알린 다음 즉시 종료됩니다.  첫 번째 인스턴스는 `StartupNextInstance` 이벤트를 처리하여 후속 인스턴스의 명령줄 인수가 무엇인지 확인한 다음 계속 실행됩니다.  
  
     이 다이어그램은 후속 인스턴스에서 첫 번째 인스턴스에 신호하는 방법을 보여 줍니다.  
  
     ![단일 인스턴스 응용 프로그램 이미지](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 `StartupNextInstance` 이벤트를 처리하여 단일 인스턴스 응용 프로그램이 동작하는 방식을 제어할 수 있습니다.  예를 들어, Microsoft Outlook은 일반적으로 단일 인스턴스 응용 프로그램으로 실행됩니다. Outlook이 실행되고 있을 때 Outlook을 다시 시작하려고 하면 포커스가 원래 인스턴스로 변경되고 다른 인스턴스는 열리지 않습니다.  
  
## 응용 프로그램 모델의 이벤트  
 응용 프로그램 모델에는 다음과 같은 이벤트가 있습니다.  
  
-   **응용 프로그램 시작**.  응용 프로그램은 시작될 때 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트를 발생시킵니다.  이 이벤트를 처리함으로써 기본 폼이 로드되기 전에 응용 프로그램을 초기화하는 코드를 추가할 수 있습니다.  또한 원하는 경우 `Startup` 이벤트를 통해 시작 프로세스 도중 응용 프로그램의 실행을 취소할 수도 있습니다.  
  
     응용 프로그램 시작 코드가 실행되고 있는 동안 시작 화면이 표시되도록 응용 프로그램을 구성할 수 있습니다.  기본적으로 응용 프로그램 모델에서는 `/nosplash` 또는 `-nosplash` 명령줄 인수가 사용된 경우 시작 화면을 표시하지 않습니다.  
  
-   **단일 인스턴스 응용 프로그램**.  단일 인스턴스 응용 프로그램의 후속 인스턴스가 시작되면 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 이벤트가 발생합니다.  이벤트는 후속 인스턴스의 명령줄 인수를 전달합니다.  
  
-   **처리되지 않은 예외**.  응용 프로그램은 처리되지 않은 예외가 발생할 경우 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트를 발생시킵니다.  이 이벤트에 대한 처리기에서 예외를 검사하여 실행을 계속할 것인지 여부를 결정할 수 있습니다.  
  
     일부 상황에서는 `UnhandledException` 이벤트가 발생하지 않습니다.  자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>을 참조하십시오.  
  
-   **네트워크 연결 변경**.  컴퓨터의 네트워크 사용 가능성이 변경되면 응용 프로그램에서 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> 이벤트를 발생시킵니다.  
  
     일부 상황에서는 `NetworkAvailabilityChanged` 이벤트가 발생하지 않습니다.  자세한 내용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>을 참조하십시오.  
  
-   **응용 프로그램 종료**.  응용 프로그램에서는 종료 신호를 보내기 위한 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트를 제공합니다.  이 이벤트 처리기에서는 응용 프로그램이 수행해야 할 닫기 및 저장 등의 작업이 완료되었는지 확인할 수 있습니다.  기본 폼이 닫힐 때 응용 프로그램이 종료되거나 모든 폼이 닫혔을 경우에만 응용 프로그램이 종료되도록 구성할 수 있습니다.  
  
## 가용성  
 기본적으로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 응용 프로그램 모델은 Windows Forms 프로젝트에 사용할 수 있습니다.  다른 시작 개체를 사용하도록 응용 프로그램을 구성하거나 사용자 지정 `Sub Main`으로 응용 프로그램 코드를 시작하는 경우 응용 프로그램 모델을 사용하려면 해당 개체나 클래스가 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 구현을 제공해야 할 수도 있습니다.  시작 개체 변경에 대한 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)