---
title: "기본 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 기본 유효성 검사
이 샘플은 `Cost` 인수가 `Price` 인수보다 작거나 같은지 확인하는 `CreateProduct` 활동으로 이루어져 있습니다.  
  
## 샘플 세부 정보  
 유효성 검사를 사용하는 작성자는 둘입니다. 그 중 하나는 활동에 대한 유효성 검사 논리를 만드는 활동 작성자이고, 다른 하나는 특정 워크플로에 대해 유효성 검사 서비스를 호출하는 워크플로 작성자입니다.이 시나리오에서 활동 작성자는 자신의 모든 활동 인스턴스의 비용이 가격을 초과하지 않도록 하려고 합니다.  
  
 활동 작성자는 \(활동 내에서\) 다음을 수행해야 합니다.  
  
-   제약 조건\(`PriceGreaterThanCost`\)을 만듭니다.모든 유효성 검사 논리가 이 제약 조건에 포함됩니다.  
  
-   <xref:System.Activities.CodeActivity%601.OnGetConstraints%2A>를 재정의하고 <xref:System.Collections.IList> 컬렉션에 제약 조건\(`PriceGreaterThanCost`\)을 추가합니다.  
  
 워크플로 작성자\(주 프로그램\)는 다음을 수행해야 합니다.  
  
-   유효성을 검사할 활동의 인스턴스\(`CreateProduct`\)를 사용하여 워크플로를 만듭니다.  
  
-   <xref:System.Activities.Validation.ConstraintViolation>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>를 호출합니다.  
  
-   \(선택 사항\) <xref:System.Activities.Validation.ConstraintViolation> 개체를 인쇄합니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 BasicValidation.sln 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`  
  
## 참고 항목