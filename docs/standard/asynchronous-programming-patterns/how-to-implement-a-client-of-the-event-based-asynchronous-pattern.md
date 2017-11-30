---
title: "방법: 이벤트 기반 비동기 패턴의 클라이언트 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>방법: 이벤트 기반 비동기 패턴의 클라이언트 구현
준수 하는 구성 요소를 사용 하는 방법은 다음 코드 예제는 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)합니다. 이 예제에 대 한 양식에서 사용 하는 `PrimeNumberCalculator` 에 설명 된 구성 요소 [하는 방법: 이벤트 기반 비동기 패턴을 지 원하는 구성 요소를 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)합니다.  
  
 이 예제를 사용 하는 프로젝트를 실행 하면 표시 됩니다는 표 및 두 개의 단추를 사용 하 여 "소수 계산기" 폼: **새 작업 시작** 및 **취소**합니다. 클릭할 수는 **새 작업 시작** 단추를 연속 해 서에서 여러 번 해 서 클릭할 때마다는 비동기 작업 계산 임의로 생성 된 테스트 수가 소수 인지 확인을 시작 합니다. 폼은 정기적으로 진행률 및 증분 결과 표시 됩니다. 각 작업 고유 작업 ID가 할당 됩니다. 계산의 결과에 표시 됩니다는 **결과** 열으로 레이블이 지정 된 테스트 수를 프라임 없으면 **복합,** 첫째 제수의 표시 됩니다.  
  
 보류 중인 모든 작업을 취소할 수 있습니다는 **취소** 단추입니다. 여러 선택 항목을 만들 수 있습니다.  
  
> [!NOTE]
>  대부분의 숫자는 소수 되지 않습니다. 여러 완료 된 작업을 수행한 후 소수를 찾지 못한 경우 단순히 더 많은 작업을 시작 하 고 결국 소수를 찾을 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
