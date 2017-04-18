---
title: "워크플로 호스팅 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 워크플로 호스팅 옵션
대부분의 [!INCLUDE[wf](../../../includes/wf-md.md)] 샘플에서는 콘솔 응용 프로그램에서 호스팅되는 워크플로를 사용하지만 이는 실제 워크플로에는 실질적으로 적합한 시나리오는 아닙니다.실제 비즈니스 응용 프로그램의 워크플로는 영구 프로세스, 즉 개발자가 작성한 Windows 서비스나 [!INCLUDE[iisver](../../../includes/iisver-md.md)] 또는 AppFabric 같은 서버 응용 프로그램에서 호스팅됩니다.이러한 방법에는 다음과 같은 차이가 있습니다.  
  
## IIS에서 Windows AppFabric을 사용하여 워크플로 호스팅  
 IIS와 AppFabric을 함께 사용하는 것은 기본적인 워크플로 호스팅 방법입니다.AppFabric을 사용하는 워크플로용 호스트 응용 프로그램은 Windows Activation Service로, 이 응용 프로그램에서는 IIS만을 통해 HTTP에 대한 종속성을 제거합니다.  
  
## IIS만 사용하여 워크플로 호스팅  
 AppFabric에서는 실행 중인 응용 프로그램의 유지 관리를 용이하게 해 주는 관리 및 모니터링 도구가 제공되므로 [!INCLUDE[iisver](../../../includes/iisver-md.md)]만 사용하는 것은 권장되지 않습니다.AppFabric으로 이동하는 데 관련된 인프라 문제가 있는 경우에만 [!INCLUDE[iisver](../../../includes/iisver-md.md)]을 단독으로 사용하여 워크플로를 호스팅해야 합니다.  
  
> [!WARNING]
>  [!INCLUDE[iisver](../../../includes/iisver-md.md)]에서는 다양한 이유로 응용 프로그램 풀을 정기적으로 재활용합니다.응용 프로그램 풀이 재활용될 때 IIS는 이전 풀에서 메시지 수락을 중지하고 새 요청을 수락하는 새 응용 프로그램 풀을 인스턴스화합니다.응답을 보낸 후 워크플로에서 작업을 계속하는 경우 [!INCLUDE[iisver](../../../includes/iisver-md.md)]에서는 수행 중인 작업을 인식하지 못하고 호스팅 응용 프로그램 풀을 재활용할 수 있습니다.이런 경우 워크플로가 중단되고 추적 서비스가 빈 이유 필드와 함께 [1004 \- WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation//1004-workflowinstanceaborted.md) 메시지를 기록합니다.  
>   
>  지속성이 사용되는 경우 호스트는 마지막 지속성 지점에서 중단된 인스턴스를 명시적으로 다시 시작해야 합니다.  
>   
>  AppFabric이 사용되는 경우 지속성이 사용되면 최종적으로 워크플로 관리 서비스가 마지막으로 성공한 지속성 지점에서 워크플로를 재개하게 됩니다.지속성이 사용되지 않고 워크플로가 요청\/응답 패턴을 벗어나 작업을 수행하는 경우에는 워크플로 중단 시 데이터가 손실됩니다.  
  
## 사용자 지정 Windows 서비스에서 워크플로 호스팅  
 사용자 지정 워크플로를 호스팅하기 위한 사용자 지정 워크플로 서비스를 만들려면 개발자가 AppFabric에서 기본적으로 제공되는 많은 기능을 복제해야 하지만 이 경우 사용자 지정 기능을 보다 유연하게 사용할 수 있다는 이점이 있습니다.이 옵션은 AppFabric을 사용할 수 없는 것이 분명한 경우에만 고려해야 합니다.