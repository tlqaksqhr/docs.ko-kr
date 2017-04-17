---
title: "활동 트리 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 활동 트리 검사
활동 트리 검사는 워크플로 응용 프로그램 작성자가 응용 프로그램에서 호스팅되는 워크플로를 검사하는 데 사용됩니다.<xref:System.Activities.WorkflowInspectionServices>를 사용하여 워크플로에서 특정 자식 활동을 검색하고, 개별 활동과 속성을 열거하며, 활동에 대한 런타임 메타데이터를 특정 시간에 캐시할 수 있습니다.이 항목에서는 <xref:System.Activities.WorkflowInspectionServices>와 이를 사용한 활동 트리 검사 방법에 대해 간략하게 설명합니다.  
  
## WorkflowInspectionServices 사용  
 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 메서드는 지정한 활동 트리의 모든 활동을 열거하는 데 사용됩니다.<xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>는 자식, 대리자 처리기, 변수 기본값, 인수 식을 비롯하여 트리 내의 모든 활동을 연결하는 열거형을 반환합니다.다음 예제에서는 <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> 및 식을 사용하여 워크플로 정의를 만듭니다.워크플로 정의를 만든 후에는 이를 호출한 다음 `InspectActivity` 메서드를 호출합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 활동을 열거하기 위해 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>를 루트 활동에 대해 호출하고 반환되는 각 활동에 대해 다시 반복적으로 호출합니다.다음 예제에서는 활동 트리의 각 활동과 식에 대한 <xref:System.Activities.Activity.DisplayName%2A>을 콘솔에 기록합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 이 샘플 코드는 다음과 같이 출력됩니다.  
  
 **List Item 1**   
**List Item 2**   
**List Item 3**   
**List Item 4**   
**List Item 5**   
**Items added to collection.**   
**Sequence**   
 **Literal\<List\<String\>\>**   
 **While**   
 **AddToCollection\<String\>**   
 **VariableValue\<ICollection\<String\>\>**   
 **LambdaValue\<String\>**   
 **LocationReferenceValue\<List\<String\>\>**   
 **LambdaValue\<Boolean\>**   
 **LocationReferenceValue\<List\<String\>\>**   
 **ForEach\<String\>**   
 **VariableValue\<IEnumerable\<String\>\>**   
 **WriteLine**   
 **DelegateArgumentValue\<String\>**   
 **Sequence**   
 **WriteLine**   
 **Literal\<String\>**  모든 활동을 열거하지 않고 특정 활동을 검색하기 위해 <xref:System.Activities.WorkflowInspectionServices.Resolve%2A>가 사용됩니다.<xref:System.Activities.WorkflowInspectionServices.Resolve%2A> 및 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>는 모두 `WorkflowInspectionServices.CacheMetadata`가 이전에 호출되지 않은 경우 메타데이터 캐싱을 수행합니다.<xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>가 호출된 경우 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>는 기존 메타데이터를 기반으로 합니다.따라서 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>를 마지막으로 호출한 이후에 트리를 변경한 경우 예기치 못한 결과가 나타날 수 있습니다.<xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>를 호출한 후 워크플로가 변경된 경우 <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 메서드를 호출하여 메타데이터를 다시 캐시할 수 있습니다.메타데이터 캐시에 대해서는 다음 단원에서 설명합니다.  
  
### 메타데이터 캐시  
 활동에 대한 메타데이터 캐시에서는 활동의 인수, 변수, 자식 활동 및 활동 대리자에 대한 설명을 빌드하고 유효성을 검사합니다.기본적으로 메타데이터는 런타임에 활동 실행이 준비될 때 캐시됩니다.워크플로 호스트 작성자가 이에 앞서 활동 또는 활동 트리에 대한 메타데이터를 캐시하려는 경우\(예: 모든 선행투자 비용을 가져오려는 경우\) <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>를 사용하여 원하는 시간에 메타데이터를 캐시할 수 있습니다.