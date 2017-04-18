---
title: "OverloadGroups | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# OverloadGroups
이 샘플은 눈여겨 봐야 할 두 가지 특징을 지닌 활동\(`CreateLocation`\)으로 구성되어 있습니다.  
  
1.  이 활동에는 몇 가지 필수 인수와 몇 가지 선택적 인수가 있습니다.  
  
2.  이 활동에서 서로 다른 두 가지 인수 집합 중 하나를 선택할 수 있습니다.  
  
 이러한 동작을 수행하는 데는 다음과 같은 두 가지 기능이 사용됩니다.  
  
-   `[isRequired]`는 특정 활동의 속성이 할당되었는지 여부를 검사하고, 속성이 할당되지 않았으면 예외를 throw합니다.  
  
-   `[OverloadGroup]`은 인수 집합을 함께 묶어 활동 사용자가 특정 집합을 선택하여 사용할 수 있도록 합니다.동일한 인스턴스 내에서 다른 오버로드 그룹의 인수를 사용할 수는 없습니다.  
  
 다른 워크플로를 설정하고 나면 <xref:System.Activities.Validation.ConstraintViolation>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>를 호출합니다.<xref:System.Activities.Validation.ConstraintViolation> 개체를 콘솔에 출력합니다.  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 **OverloadGroups.sln** 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## 참고 항목