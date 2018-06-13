---
title: 외부 활동 유효성 검사
ms.date: 03/30/2017
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
ms.openlocfilehash: 1ceb1d2b2f7e8926479fa4c53cfb82a5cdb3a83f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517802"
---
# <a name="external-activity-validation"></a>외부 활동 유효성 검사
이 샘플에서는 직접 작성하지 않은 기본 제공 활동에 유효성 검사 논리를 추가하는 방법을 보여 줍니다. 유효성 검사 논리는 워크플로에 있는 모든 <xref:System.Activities.Statements.If> 활동의 <xref:System.Activities.Statements.If.Then%2A> 속성이 설정되거나 <xref:System.Activities.Statements.If.Else%2A> 속성이 설정되도록 적용하는 것으로 구성됩니다. 또한 유효성 검사 논리에는 워크플로에 있는 모든 <xref:System.Activities.Statements.Pick> 활동에 둘 이상의 분기가 있는지 확인하고, 그렇지 않은 경우 경고를 생성하는 것도 포함됩니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플에서는 유효성을 검사할 각 활동, 즉 <xref:System.Activities.Statements.If> 활동과 <xref:System.Activities.Statements.Pick> 활동의 인스턴스를 사용하여 워크플로를 만듭니다. 각 유효성 검사 동작마다 <xref:System.Activities.Validation.Constraint>가 만들어집니다. 이 샘플에서 만들어지는 제약 조건은 `ConstraintError_IfShouldHaveThenOrElse`와 `ConstraintWarning_PickHasOneBranch`입니다. 그런 다음 이러한 제약 조건이 `AdditionalConstraints` 인스턴스의 <xref:System.Activities.Validation.ValidationSettings> 컬렉션에 추가됩니다. 마지막으로, `static`의 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A><xref:System.Activities.Validation.ActivityValidationServices> 메서드를 호출하여 워크플로의 활동에 대한 유효성을 검사하고 유효성 검사 결과를 콘솔에 출력합니다.  
  
> [!NOTE]
>  모든 활동에 정책 제약 조건을 추가할 수 있습니다. 예를 들어 <xref:System.Activities.Statements.Sequence> 또는 <xref:System.Activities.Statements.Parallel> 활동에 정책 제약 조건을 추가할 수 있습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ExternalActivityValidation.sln 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`