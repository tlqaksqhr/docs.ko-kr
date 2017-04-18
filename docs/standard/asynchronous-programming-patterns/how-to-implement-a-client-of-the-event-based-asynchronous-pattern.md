---
title: "How to: Implement a Client of the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Implement a Client of the Event-based Asynchronous Pattern
다음 코드 예제에서는 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)를 따르는 구성 요소의 사용 방법을 보여 줍니다.  이 예제의 폼은 [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)에 설명되어 있는  `PrimeNumberCalculator`  구성 요소를 사용합니다.  
  
 이 예제를 사용하는 프로젝트를 실행하면 모눈과 2개의 단추 **Start New Task** 및 **Cancel**이 있는 "Prime Number Calculator"가 표시됩니다.  **Start New Task** 단추를 연속해서 여러 번 클릭하면 클릭할 때마다 비동기 작업이 계산을 시작하여 임의로 생성된 테스트 수가 소수인지 확인합니다.  이 폼은 진행률과 누적 결과를 주기적으로 표시합니다.  각 작업에는 고유한 작업 ID가 할당됩니다.  **Result** 열에 계산 결과가 표시되고 테스트 수가 소수가 아니면 용어 **Composite**와 첫 번째 약수가 표시됩니다.  
  
 **Cancel** 단추를 클릭하면 보류 중인 작업을 취소할 수 있습니다.  한꺼번에 여러 항목을 선택할 수 있습니다.  
  
> [!NOTE]
>  대부분의 수는 소수가 아닙니다.  여러 연산을 완료한 후에 소수를 찾지 못하더라도 추가 연산을 계속 수행하여 소수를 더 찾을 수 있습니다.  
  
## 예제  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## 참고 항목  
 <xref:System.ComponentModel.AsyncOperation>   
 <xref:System.ComponentModel.AsyncOperationManager>   
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>