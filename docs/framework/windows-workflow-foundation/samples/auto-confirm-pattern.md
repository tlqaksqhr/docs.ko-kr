---
title: "자동 확인 패턴"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 668aec65-78d3-4636-9c7b-deed643a18f9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3595e501341f64883ce2552f0a3c0850691f38c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="auto-confirm-pattern"></a>자동 확인 패턴
이 샘플은 사용자 지정 `AutoConfirmScope` 활동을 보여 주기 위해 실행하는 세 가지 시나리오로 구성되어 있습니다. 첫 번째 시나리오에서는 두 번째 시나리오와 세 번째 시나리오가 `AutoConfirmScope`에 중첩된 네 개의 보정 가능한 활동으로 구성된 시퀀스의 성공적인 실행을 보여 줍니다. 두 번째 시나리오에서는 네 번째 <xref:System.Activities.Statements.CompensableActivity>가 실행된 후 예외가 발생한다는 점만 제외하고 동일한 시퀀스를 보여 줍니다. 세 번째 시나리오에서는 두 번째 `AutoConfirmScope`가 완료된 후 <xref:System.Activities.Statements.CompensableActivity>에서 예외가 발생한다는 점만 제외하고 동일한 시퀀스를 보여 줍니다.  
  
 이 샘플에서는 범위가 성공적으로 완료되면 보정 가능한 모든 자식 활동이 확인되는 자동 확인 패턴을 보여 줍니다. 이 패턴에서는 보정 가능한 모든 자식 활동의 수명 주기를 정의합니다. 수명 주기는 활동을 더 이상 보정하거나 확인할 수 없는 시점까지의 기간을 말합니다.  
  
 범위는 <xref:System.Activities.Statements.TryCatch> 가 내부 <xref:System.Activities.Statements.TryCatch.Try%2A>인 <xref:System.Activities.Statements.CompensableActivity>로 구성됩니다. `AutoConfirmScope`의 사용자 지정 본문은 내부 <xref:System.Activities.Statements.CompensableActivity>의 본문입니다. 이 내부 <xref:System.Activities.Statements.CompensableActivity>가 완료되면 <xref:System.Activities.Statements.CompensationToken>이 out 인수로 생성됩니다. `AutoConfirmScope`는 <xref:System.Activities.Statements.TryCatch.Finally%2A>를 사용하여 토큰이 생성되었는지 확인한 후 생성되었으면 내부 <xref:System.Activities.Statements.CompensableActivity>를 확인합니다. 내부 <xref:System.Activities.Statements.CompensableActivity>는 본문에 있을 수 있는 보정 가능한 활동에 대한 기본 보정을 호출합니다.  
  
 첫 번째 시나리오에서는 워크플로의 성공적인 실행을 보여 주고, 워크플로가 완료되고 보정 가능한 첫 번째 활동과 네 번째 활동이 확인될 때 보정 가능한 두 번째 활동과 세 번째 활동이 이미 확인되었음을 보여 줍니다. 여기서 확인 순서는 3, 2, 4, 1순입니다.  
  
 두 번째 시나리오에서는 보정 가능한 네 번째 활동이 완료된 후의 예외를 보여 줍니다. 보정 가능한 두 번째 활동과 세 번째 활동은 이미 확인되었으므로 영향을 받지 않지만 첫 번째 활동과 네 번째 활동은 보정됩니다. 여기에서는 세 번째 활동이 확인되고, 두 번째 활동이 확인된 후 네 번째 활동이 보정되고 첫 번째 활동이 보정됩니다.  
  
 마지막 시나리오에서는 `AutoConfirmScope`의 실패한 실행을 보여 줍니다. 이 시나리오에서는 두 번째 <xref:System.Activities.Statements.CompensableActivity>가 완료된 후 예외가 발생합니다. 보정 가능한 세 번째 활동과 네 번째 활동은 실행되지 않았으므로 영향을 받지 않습니다. 범위가 성공적으로 완료되지 않았으므로 두 번째 <xref:System.Activities.Statements.CompensableActivity>는 확인되지 않습니다. 여기에서는 두 번째 활동이 보정된 후 첫 번째 활동이 보정됩니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 AutoConfirmSample.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Compensation\AutoConfirm`