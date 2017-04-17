---
title: "외부 활동 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 외부 활동 유효성 검사
이 샘플에서는 직접 작성하지 않은 기본 제공 활동에 유효성 검사 논리를 추가하는 방법을 보여 줍니다.유효성 검사 논리는 워크플로에 있는 모든 <xref:System.Activities.Statements.If> 활동의 <xref:System.Activities.Statements.If.Then%2A> 속성이 설정되거나 <xref:System.Activities.Statements.If.Else%2A> 속성이 설정되도록 적용하는 것으로 구성됩니다.또한 유효성 검사 논리에는 워크플로에 있는 모든 <xref:System.Activities.Statements.Pick> 활동에 둘 이상의 분기가 있는지 확인하고, 그렇지 않은 경우 경고를 생성하는 것도 포함됩니다.  
  
## 샘플 세부 정보  
 이 샘플에서는 유효성을 검사할 각 활동, 즉 <xref:System.Activities.Statements.If> 활동과 <xref:System.Activities.Statements.Pick> 활동의 인스턴스를 사용하여 워크플로를 만듭니다.각 유효성 검사 동작마다 <xref:System.Activities.Validation.Constraint>가 만들어집니다.이 샘플에서 만들어지는 제약 조건은 `ConstraintError_IfShouldHaveThenOrElse`와 `ConstraintWarning_PickHasOneBranch`입니다.그런 다음 이러한 제약 조건이 <xref:System.Activities.Validation.ValidationSettings> 인스턴스의 `AdditionalConstraints` 컬렉션에 추가됩니다.마지막으로, <xref:System.Activities.Validation.ActivityValidationServices>의 `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 메서드를 호출하여 워크플로의 활동에 대한 유효성을 검사하고 유효성 검사 결과를 콘솔에 출력합니다.  
  
> [!NOTE]
>  모든 활동에 정책 제약 조건을 추가할 수 있습니다.예를 들어 <xref:System.Activities.Statements.Sequence> 또는 <xref:System.Activities.Statements.Parallel> 활동에 정책 제약 조건을 추가할 수 있습니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ExternalActivityValidation.sln 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`  
  
## 참고 항목