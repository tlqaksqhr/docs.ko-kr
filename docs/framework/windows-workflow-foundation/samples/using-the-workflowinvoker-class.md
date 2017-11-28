---
title: Using the WorkflowInvoker Class
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f5310b2adefa24d2d16733965395a34cc5cb69d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-workflowinvoker-class"></a>Using the WorkflowInvoker Class
이 샘플에서는 <xref:System.Activities.WorkflowInvoker> 클래스를 사용하여 활동을 마치 메서드처럼 호출하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 <xref:System.Activities.WorkflowInvoker> 클래스를 사용하면 활동을 매우 간단하게 실행할 수 있습니다. 이 클래스는 활동을 마치 메서드 호출과 같이 직접 실행하기 위한 것으로, 활동을 실행하는 데 다른 호스팅 변형에서 제공하는 컨트롤 인프라가 필요하지 않은 경우에 사용할 수 있는 간단하면서도 성능이 우수하고 사용하기 쉬운 API입니다.  
  
 파생 되는 사용자 지정 활동을 사용 하 여 샘플 <xref:System.Activities.CodeActivity%601>< Int32\> 라는 `Add` 두 개를 추가 하는 <xref:System.Activities.InArgument%601>, `X` 및 `Y`, 반환 하 고는 `Result` <xref:System.Activities.OutArgument%601>합니다. (<xref:System.Activities.CodeActivity%601>\<T >에서 파생 <xref:System.Activities.Activity%601>< T\>을는 <xref:System.Activities.OutArgument%601> \<T > 명명 된 `Result`.) A `Dictionary` \<문자열, 개체 >를 통해 호출 되는 활동에 인수를 전달 하는 데 사용 <xref:System.Activities.WorkflowInvoker>합니다. 사전의 키는 호출되는 활동의 인수 이름에 해당합니다. 특정 키와 연결된 값은 키가 식별하는 인수에 바인딩됩니다.  
  
 이 샘플에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 호출하고 `X` 및 `Y`의 값이 들어 있는 사전을 전달합니다. <xref:System.Activities.WorkflowInvoker> 클래스는 이러한 값을 `Add` 활동의 인수에 바인딩하고 활동을 실행한 다음 결과를 반환합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Invoker.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`  
  
## <a name="see-also"></a>참고 항목
