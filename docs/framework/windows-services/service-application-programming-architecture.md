---
title: "서비스 응용 프로그램 프로그래밍 아키텍처 | Microsoft Docs"
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
  - "ServiceBase 클래스, 서비스 상태"
  - "ServiceController 클래스"
  - "ServiceController 구성 요소, 프로그래밍 아키텍처"
  - "ServiceProcessInstaller 클래스, 서비스 응용 프로그램 코드 모델"
  - "서비스, 프로그래밍 아키텍처"
  - "서비스, 상태"
  - "Windows 서비스 응용 프로그램, 코드 모델"
  - "Windows 서비스 응용 프로그램, 상태"
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# 서비스 응용 프로그램 프로그래밍 아키텍처
Windows 서비스 응용 프로그램은 <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName> 클래스에서 상속되는 클래스를 기반으로 합니다.  이 클래스에서 메서드를 재정의하고 메서드의 기능을 정의하여 서비스의 동작 방식을 지정합니다.  
  
 서비스 작성과 관련된 주 클래스는 다음과 같습니다.  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=fullName> — 서비스를 만들 때 <xref:System.ServiceProcess.ServiceBase> 클래스에서 메서드를 재정의하고, 코드를 정의하여 현재 상속된 클래스에서 서비스가 작동하는 방식을 지정합니다.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=fullName> 및 <xref:System.ServiceProcess.ServiceInstaller?displayProperty=fullName> — 이들 클래스를 사용하여 서비스를 설치하고 제거합니다.  
  
 또한 <xref:System.ServiceProcess.ServiceController>로 명명된 클래스를 사용하여 서비스 자체를 조작할 수 있습니다.  이 클래스는 서비스 작성과 관련되지 않지만 서비스를 시작 및 중지하고, 서비스에 명령을 전달하고, 일련의 열거형을 반환하는 데 사용할 수 있습니다.  
  
## 서비스 동작 정의  
 서비스 클래스에서는 서비스의 상태가 변경될 때 서비스 제어 관리자에서 발생시킬 기본 클래스 함수를 재정의합니다.  <xref:System.ServiceProcess.ServiceBase> 클래스는 다음 메서드를 노출하며 이 메서드를 재정의하여 사용자 지정 동작을 추가할 수 있습니다.  
  
|메서드|재정의|  
|---------|---------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|서비스가 실행을 시작할 때 수행할 동작을 나타냅니다.  서비스가 필요한 작업을 수행할 수 있도록 이 프로시저에 코드를 작성해야 합니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|서비스가 일시 중지되었을 때 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|서비스의 실행이 중지되었을 때 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|서비스가 일시 중지된 후 다시 정상 작동을 시작할 때 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|서비스가 실행되고 있을 경우 시스템이 종료되기 직전에 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|서비스가 사용자 지정 명령을 받았을 때 수행할 동작을 나타냅니다.  사용자 지정 명령에 대한 자세한 내용은 MSDN Online을 참조하십시오.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|배터리 부족이나 작업 일시 중단 등 전원 관리 이벤트가 수신될 때 서비스가 응답할 방법을 나타냅니다.|  
  
> [!NOTE]
>  이러한 메서드는 서비스의 수명 동안 서비스가 이동하는 상태, 즉 하나의 상태에서 다음 상태로의 서비스 전환을 나타냅니다.  예를 들어, 서비스는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A>가 호출되기 전에 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 명령에 응답하지 않습니다.  
  
 이와 관련된 몇 가지 다른 속성 및 메서드에는  제공합니다.  
  
-   <xref:System.ServiceProcess.ServiceBase> 클래스의 <xref:System.ServiceProcess.ServiceBase.Run%2A> 메서드.  서비스에 대한 주 진입점입니다.  Windows 서비스 템플릿을 사용하여 서비스를 만들 때 응용 프로그램의 `Main` 메서드에 서비스를 실행하는 코드가 삽입됩니다.  코드는 다음과 비슷합니다.  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  위의 예제는 <xref:System.ServiceProcess.ServiceBase> 형식 배열을 사용합니다. 이 배열에 응용 프로그램이 포함하는 각 서비스를 추가한 다음 모든 서비스를 함께 실행할 수 있습니다.  그러나 하나의 서비스만을 만드는 경우에는 배열을 사용하지 않고 <xref:System.ServiceProcess.ServiceBase>에서 상속한 새로운 개체를 선언한 다음 이 개체를 실행하면 됩니다.  예제를 보려면 [방법: 프로그래밍 방식으로 서비스 작성](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)을 참조하십시오.  
  
-   <xref:System.ServiceProcess.ServiceBase> 클래스에 있는 일련의 속성.  이 속성은 서비스에서 호출할 수 있는 메서드를 지정합니다.  예를 들어, <xref:System.ServiceProcess.ServiceBase.CanStop%2A> 속성을 `true`로 설정하면 서비스의 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드를 호출할 수 있습니다.  <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> 속성을 `true`로 설정하면 <xref:System.ServiceProcess.ServiceBase.OnPause%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 메서드를 호출할 수 있습니다.  이러한 속성 중 하나를 `true`로 설정한 다음에는 관련 메서드에 대한 처리를 재정의해야 합니다.  
  
    > [!NOTE]
    >  서비스는 적어도 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A>을 재정의해야 유용하게 사용할 수 있습니다.  
  
 또한 <xref:System.ServiceProcess.ServiceController>를 호출한 구성 요소를 사용하여 기존 서비스의 동작과 통신하고 이를 제어할 수 있습니다.  
  
## 참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)