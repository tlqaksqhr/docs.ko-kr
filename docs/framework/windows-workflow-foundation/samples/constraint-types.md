---
title: "제약 조건 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f78337ebc643b584b89f26ca39e400fb8e6e9c26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="constraint-types"></a>제약 조건 형식
이 샘플에서는 워크플로에 제약 조건을 적용하는 서로 다른 두 가지 방법을 보여 줍니다. 그 중 하나는 활동 내부에서(빌드) 적용하는 방법이고, 다른 하나는 활동 외부에서(정책) 적용하는 방법입니다. 이 시나리오에서는 타사 소프트웨어 회사의 활동 작성자가 두 인수 사이의 관계에 대한 유효성을 검사하려는 경우를 가정합니다. 이 경우 비용이 금액을 초과하지 않아야 합니다. 이는 일반적인 유효성 검사 빌드 제약 조건입니다.  
  
 그런 다음 가게 주인이 이 일반적인 활동에 다른 유효성 검사를 더 추가합니다. 이 사람은 자신의 가게에서 취급하는 상품 대부분의 가격이 9.99달러를 넘지 않기를 원합니다. 따라서 이 가게 주인은 `CreateProduct` 활동을 기반으로 정책 제약 조건을 사용합니다.  
  
 이 샘플의 내용은 다음과 같습니다.  
  
 활동 작성자(빌드)가 다음을 수행해야 합니다.  
  
-   제약 조건(`PriceGreaterThanCost`)을 만듭니다. 모든 유효성 검사 논리가 이 제약 조건에 포함됩니다.  
  
-   `System.Activities.CodeActivity.OnGetConstraints()`를 재정의하고 `PriceGreaterThanCost` 컬렉션에 제약 조건(<xref:System.Collections.IList>)을 추가합니다.  
  
 워크플로 작성자(정책)가 다음을 수행해야 합니다.  
  
-   유효성을 검사할 활동의 인스턴스(`CreateProduct`)를 사용하여 워크플로를 만듭니다.  
  
-   제약 조건(`MaxPrice`)을 만듭니다.  
  
-   <xref:System.Activities.Validation.ValidationSettings> 인스턴스(`validationSettings`)를 만들고 `MaxPrice` 컬렉션에 제약 조건(`AdditionalConstraints`)을 추가합니다. 이때 워크플로 작성자는 순차 또는 병렬 등 임의의 활동에 정책 제약 조건을 추가할 수 있습니다.  
  
-   <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 개체의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.ValidationError>를 호출합니다.  
  
-   (선택 사항) <xref:System.Activities.Validation.ValidationError> 개체를 인쇄합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ConstraintTypes.sln 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`  
  
## <a name="see-also"></a>참고 항목
