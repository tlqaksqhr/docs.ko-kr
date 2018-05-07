---
title: 기본 유효성 검사
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: db7db339d0b7bfd756d8ba22fb8488b8f7ecfa3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="basic-validation"></a>기본 유효성 검사
이 샘플은 `CreateProduct` 인수가 `Cost` 인수보다 작거나 같은지 확인하는 `Price` 활동으로 이루어져 있습니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 유효성 검사를 사용하는 작성자는 둘입니다. 그 중 하나는 활동에 대한 유효성 검사 논리를 만드는 활동 작성자이고, 다른 하나는 특정 워크플로에 대해 유효성 검사 서비스를 호출하는 워크플로 작성자입니다. 이 시나리오에서 활동 작성자는 자신의 모든 활동 인스턴스의 비용이 가격을 초과하지 않도록 하려고 합니다.  
  
 활동 작성자는 (활동 내에서) 다음을 수행해야 합니다.  
  
-   제약 조건(`PriceGreaterThanCost`)을 만듭니다. 모든 유효성 검사 논리가 이 제약 조건에 포함됩니다.  
  
-   `System.Activities.CodeActivity.OnGetConstraints()`를 재정의하고 `PriceGreaterThanCost` 컬렉션에 제약 조건(<xref:System.Collections.IList>)을 추가합니다.  
  
 워크플로 작성자(주 프로그램)는 다음을 수행해야 합니다.  
  
-   유효성을 검사할 활동의 인스턴스(`CreateProduct`)를 사용하여 워크플로를 만듭니다.  
  
-   <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.ValidationError>를 호출합니다.  
  
-   (선택 사항) <xref:System.Activities.Validation.ValidationError> 개체를 인쇄합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 BasicValidation.sln 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`