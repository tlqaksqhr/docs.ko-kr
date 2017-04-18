---
title: "활동 유효성 검사 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 활동 유효성 검사 구성
활동 유효성 검사를 사용하면 활동 작성자 및 사용자가 활동을 실행하기 이전에 활동 구성 오류를 식별하여 보고할 수 있습니다.[!INCLUDE[wf](../../../includes/wf-md.md)]에서는 다음과 같은 3가지 유형의 활동 유효성 검사를 제공합니다.  
  
-   `RequiredArgument` 및 `OverloadGroup` 특성  
  
-   필수 코드 기반 유효성 검사  
  
-   선언적 제약 조건  
  
 `RequiredArgument` 및 `OverloadGroup` 특성은 활동의 특정 인수가 필수 항목임을 나타냅니다.필수 코드 기반 유효성 검사를 사용하면 활동 자체에 대한 유효성을 쉽게 검사할 수 있고, 선언적 제약 조건을 사용하면 활동 및 활동과 포함된 워크플로와의 관계에 대한 유효성을 검사할 수 있습니다.활동이 유효성 검사 요구 사항에 따라 적절하게 구성되지 않은 경우 유효성 검사 오류 및 경고가 반환됩니다.Workflow Designer를 사용하여 포함된 워크플로를 만드는 경우에는 유효성 검사 오류 및 경고가 디자이너에 표시됩니다.Workflow Designer 외부에서 워크플로를 만드는 경우에는 워크플로가 호출되면 유효성 검사 오류가 반환됩니다.워크플로를 만드는 방법에 상관없이 유효성 검사 오류가 있는 워크플로는 실행할 수 없습니다.이 단원에서는 이러한 유형의 활동 유효성 검사의 개요와 활동 유효성 검사를 호출하는 방법을 간략하게 설명합니다.  
  
## 단원 내용  
 [필수 인수 및 오버로드 그룹](../../../docs/framework/windows-workflow-foundation//required-arguments-and-overload-groups.md)  
 `RequiredArgument` 및 `OverloadGroup` 특성을 사용하여 유효성 검사를 수행하는 방법에 대해 설명합니다.  
  
 [명령 코드 기반 유효성 검사](../../../docs/framework/windows-workflow-foundation//imperative-code-based-validation.md)  
 <xref:System.Activities.CodeActivity> 및 <xref:System.Activities.NativeActivity> 기반 활동에 대해 코드 기반 유효성 검사를 사용하는 방법에 대해 설명합니다.  
  
 [선언적 제약 조건](../../../docs/framework/windows-workflow-foundation//declarative-constraints.md)  
 선언적 제약 조건을 사용하여 복잡한 활동 유효성 검사를 수행하는 방법에 대해 설명합니다.  
  
 [활동 유효성 검사 호출](../../../docs/framework/windows-workflow-foundation//invoking-activity-validation.md)  
 활동 유효성 검사가 자동으로 호출되는 시기와 유효성 검사를 명시적으로 호출하는 방법에 대해 설명합니다.  
  
## 참조  
  
## 관련 단원