---
title: "Using the WorkflowInvoker Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Using the WorkflowInvoker Class
이 샘플에서는 <xref:System.Activities.WorkflowInvoker> 클래스를 사용하여 활동을 마치 메서드처럼 호출하는 방법을 보여 줍니다.  
  
## 샘플 세부 정보  
 <xref:System.Activities.WorkflowInvoker> 클래스를 사용하면 활동을 매우 간단하게 실행할 수 있습니다.이 클래스는 활동을 마치 메서드 호출과 같이 직접 실행하기 위한 것으로,활동을 실행하는 데 다른 호스팅 변형에서 제공하는 컨트롤 인프라가 필요하지 않은 경우에 사용할 수 있는 간단하면서도 성능이 우수하고 사용하기 쉬운 API입니다.  
  
 이 샘플에서는 `Add`라는 <xref:System.Activities.CodeActivity%601>\<Int32\>에서 파생된 사용자 지정 활동을 사용하며 이 활동은 두 개의 <xref:System.Activities.InArgument%601>인 `X` 및 `Y`를 추가하고 `Result`<xref:System.Activities.OutArgument%601>를 반환합니다.<xref:System.Activities.CodeActivity%601>\<T\>는 `Result`라는 <xref:System.Activities.OutArgument%601>\<T\>가 있는 <xref:System.Activities.Activity%601>\<T\>에서 파생됩니다. `Dictionary`\<string, object\>는 <xref:System.Activities.WorkflowInvoker>를 통해 호출되는 활동에 인수를 전달하는 데 사용됩니다.사전의 키는 호출되는 활동의 인수 이름에 해당합니다.특정 키와 연결된 값은 키가 식별하는 인수에 바인딩됩니다.  
  
 이 샘플에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 호출하고 `X` 및 `Y`의 값이 들어 있는 사전을 전달합니다.<xref:System.Activities.WorkflowInvoker> 클래스는 이러한 값을 `Add` 활동의 인수에 바인딩하고 활동을 실행한 다음 결과를 반환합니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Invoker.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`  
  
## 참고 항목