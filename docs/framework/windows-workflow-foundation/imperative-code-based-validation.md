---
title: "명령 코드 기반 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79e50c9cc756915ffc1a2f376d6b46469c85dbf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imperative-code-based-validation"></a>명령 코드 기반 유효성 검사
명령형 코드 기반 유효성 검사를 이용하면 활동 자체에서 활동 유효성 검사를 간단히 실행할 수 있으며 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 및 <xref:System.Activities.NativeActivity>의 파생 활동에도 사용할 수 있습니다. 유효성 검사 오류 또는 경고를 판단하는 유효성 검사 코드가 활동에 추가됩니다.  
  
## <a name="using-code-based-validation"></a>코드 기반 유효성 검사 사용  
 코드 기반 유효성 검사는 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 및 <xref:System.Activities.NativeActivity>의 파생 활동에서 지원됩니다. <xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의에 유효성 검사 코드를 배치할 수 있으며, 메타데이터 인수에 유효성 검사 오류 또는 경고를 추가할 수 있습니다. 다음 예제에서에서 가져온는 [기본 유효성 검사](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) 샘플링 하는 경우는 `Cost` 보다 크면는 `Price`, 메타 데이터에 유효성 검사 오류가 추가 됩니다.  
  
> [!NOTE]
>  `Cost` 및 `Price`는 활동에 대한 인수는 아니지만 디자인 타임에 설정되는 속성입니다. 따라서 이러한 값은 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의에서 유효성을 검사할 수 있습니다. 인수를 통해 흐르는 데이터 값은 런타임이 될 때가지 흐르지 않으므로 디자인 타임에서 유효성을 검사할 수 없습니다. 활동 인수는 `RequiredArgument` 특성 및 오버로드 그룹을 사용하여 바인딩되도록 유효성을 검사할 수 있습니다. 이 예제 코드에서는 `RequiredArgument` 인수에 대한 `Description` 특성을 확인하여 바인딩되어 있지 않을 경우 유효성 검사 오류가 발생합니다. 필수 인수에 대해서는 설명 [필요한 인수 및 오버 로드 그룹](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)합니다.  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 기본적으로 <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>가 호출되면 메타데이터에 유효성 검사 오류가 추가됩니다. 유효성 검사 경고를 추가하려면 <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>를 취하는 <xref:System.Activities.Validation.ValidationError> 오버로드를 사용하고 <xref:System.Activities.Validation.ValidationError> 속성을 설정하여 <xref:System.Activities.Validation.ValidationError.IsWarning%2A>가 경고를 나타내도록 지정합니다.  
  
 Workflow Designer에서 워크플로를 수정하면 유효성 검사가 수행되어 Workflow Designer에 유효성 검사 오류 또는 경고가 표시됩니다. 워크플로를 호출하면 런타임에도 유효성 검사가 수행되며 유효성 검사 오류가 발생할 경우 기본 유효성 검사 논리에 따라 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]유효성 검사 호출 및 모든 유효성 검사 경고 또는 오류를 액세스 참조 [활동 유효성 검사 호출](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)합니다.  
  
 <xref:System.Activities.CodeActivity.CacheMetadata%2A>에서 throw되는 모든 예외는 유효성 검사 오류로 처리되지 않습니다. 이러한 예외는 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>에 대한 호출에서 이스케이프되며 호출자가 처리해야 합니다.  
  
 코드 기반 유효성 검사는 해당 코드가 포함된 활동의 유효성을 검사하는 데 유용하지만 워크플로의 다른 활동은 볼 수 없습니다. 선언적 제약 조건은 유효성 검사는 워크플로의 다른 활동 및 활동 간 관계의 유효성을 검사 하는 기능을 제공 하며에 대해서는 [선언적 제약 조건을](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) 항목입니다.
