---
title: "활동 관계 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 활동 관계 유효성 검사
이 샘플은 `CreateCity`, `CreateState` 및 `CreateCountry`의 세 가지 활동으로 구성됩니다.`CreateCity`는 `CreateState` 활동 안에 있어야 하고, `CreateState`는 `CreateCountry` 활동 안에 있어야 합니다.이 샘플에서 사용할 유효성 검사 논리는 `CreateState` 활동의 경우 코드로 되어 있고 `CreateCity` 활동의 경우 XAML로 되어 있습니다.두 제약 조건의 동작은 동일합니다.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서는 개발자가 활동 간 관계의 유효성을 검사할 수 있도록 다음과 같은 세 가지 도우미 활동을 제공합니다.  
  
 <xref:System.Activities.Validation.GetParentChain>  
 현재 노드의 부모에 속하는 모든 활동의 컬렉션을 제공합니다.  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 현재 노드를 제외하고 현재 노드의 하위 트리에 속하는 모든 활동의 컬렉션을 제공합니다.  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 현재 노드와 동일한 트리에 있는 모든 활동의 컬렉션을 제공합니다.  
  
 이 샘플에서 <xref:System.Activities.Statements.ForEach%601> 활동은 <xref:System.Activities.Validation.GetParentChain>에서 반환하는 컬렉션의 단계를 수행하는 데 사용됩니다.컬렉션에 있는 모든 요소의 형식은 `CreateCountry`\(`CreateCity`의 유효성을 검사하는 경우에는 `CreateState`\)와 비교되며, 일치하는 항목이 있으면 결과 플래그가 `true`로 설정됩니다.마지막으로, 결과 플래그가 `false`로 설정되어 있는 경우 <xref:System.Activities.Validation.AssertValidation>은 유효성 검사 오류를 생성하는 데 사용됩니다.  
  
### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ContainmentValidation.sln 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드합니다.  
  
3.  CTRL\+F5를 눌러 프로그램을 시작합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`  
  
## 참고 항목