---
title: "서비스 응용 프로그램 프로그래밍 아키텍처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a>서비스 응용 프로그램 프로그래밍 아키텍처
상속 되는 클래스를 기반으로 하는 Windows 서비스 응용 프로그램은 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 클래스입니다. 이 클래스에서 메서드를 재정의 하 고이 정보를 서비스의 작동 방식을 결정할 수에 대 한 기능을 정의 합니다.  
  
 서비스 만들기에 관련 된 기본 클래스는입니다.  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>— 메서드를 재정의할이 작업은 <xref:System.ServiceProcess.ServiceBase> 서비스를 만들 때 클래스와이 서비스 함수 클래스를 상속 하는 방법을 결정 하는 코드를 정의 합니다.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>및 <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> -이러한 클래스를 사용 하 여 설치 하 고 서비스를 제거 합니다.  
  
 또한 라는 클래스 <xref:System.ServiceProcess.ServiceController> 는 서비스 자체를 조작 하는 데 사용할 수 있습니다. 이 클래스는 서비스 만들기에 관련 된 않으며 시작 하 고 서비스를 중지 하 고에 명령을 전달 하 고 일련의 열거형을 반환 하는 데 사용 될입니다.  
  
## <a name="defining-your-services-behavior"></a>서비스의 동작 정의  
 서비스 클래스에서 서비스의 상태 서비스 제어 관리자에서 변경 될 때 수행 되는 기본 클래스 함수를 재정의 합니다. <xref:System.ServiceProcess.ServiceBase> 클래스 사용자 지정 동작을 추가 하기 위해 재정의할 수 있는 다음과 같은 메서드를 노출 합니다.  
  
|메서드|재정의 합니다.|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|서비스가 실행을 시작할 때 어떤 작업을 수행 해야 나타냅니다. 유용한 작업을 수행 하려면 해당 서비스에 대해이 절차의 코드를 작성 해야 합니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|서비스 일시 중지 될 때 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|서비스가 중지 된 경우 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|서비스 일시 중지 된 후 일반 기능을 다시 시작 될 때 수행할 동작을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|서비스가 해당 시점에 실행 중인 경우 시스템이, 종료 하기 전에 수행할 작업을 나타냅니다.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|서비스 사용자 지정 명령을 수신할 때 수행할 동작을 나타냅니다. 사용자 지정 명령에 대 한 자세한 내용은 온라인 MSDN 참조 하십시오.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|배터리 부족 또는 일시 중단 된 작업과 같이 전원 관리 이벤트가 수신 되 면 서비스가 해야 응답 하는 방법을 나타냅니다.|  
  
> [!NOTE]
>  이러한 메서드는 서비스의 수명이;를 통해 이동 하는 상태를 나타내는 다음 한 상태에서 서비스 전환 됩니다. 예를 들어는 가져올 수 없습니다에 응답 하는 서비스는 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 하기 전에 명령을 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 가 호출 되었습니다.  
  
 다른 여러 속성 및 관심 있는 메서드가 있습니다. 여기에는 다음이 포함됩니다.  
  
-   <xref:System.ServiceProcess.ServiceBase.Run%2A> 에서 메서드는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다. 이 서비스에 대 한 주 진입점입니다. Windows 서비스 템플릿을 사용 하 여 서비스를 만들면 응용 프로그램의 코드가 삽입 됩니다 `Main` 서비스를 실행 하는 메서드. 이 코드는 다음과 같습니다.  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  이 예에서는 형식의 배열을 사용 하 여 <xref:System.ServiceProcess.ServiceBase>, 응용 프로그램을 포함 하는 각 서비스를 추가할 수 있습니다 및 된 다음 모든 서비스 수를 함께 실행할 수 있습니다. 그러나만 단일 서비스를 만드는 경우 선택할 수 있습니다는 배열을 사용를 단순히에서 상속 하는 새 개체를 선언 하는 <xref:System.ServiceProcess.ServiceBase> 하 고 실행 합니다. 예를 들어 참조 [하는 방법: 프로그래밍 방식으로 서비스 작성](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)합니다.  
  
-   일련의 속성에는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다. 이러한 서비스에서 어떤 메서드를 호출할 수를 결정 합니다. 예를 들어는 <xref:System.ServiceProcess.ServiceBase.CanStop%2A> 속성이로 설정 되어 `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 서비스에서 메서드를 호출할 수 있습니다. 때는 <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> 속성이 `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 메서드를 호출할 수 있습니다. 이러한 속성을 설정 하면 `true`, 그런 다음 재정의 하 고 연결된 된 메서드에 대 한 처리 해야 합니다.  
  
    > [!NOTE]
    >  이상 서비스를 재정의 해야 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 유용 하 게 되려면 합니다.  
  
 라는 구성 요소를 사용할 수도 있습니다는 <xref:System.ServiceProcess.ServiceController> 와 통신 하 고 기존 서비스의 동작을 제어 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)
