---
title: "연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현"
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
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a>연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현
구현 하 여 비동기 기능을 제공할 상당한 지연을 일으킬 수 있는 일부 작업을 사용 하 여 클래스를 작성 하는 경우 고려는 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)합니다.  
  
 이 연습에서는 이벤트 기반 비동기 패턴을 구현 하는 구성 요소를 만드는 방법을 설명 합니다. 도우미 클래스를 사용 하는 것의 <xref:System.ComponentModel?displayProperty=nameWithType> 구성 요소가 모든 응용 프로그램 모델에서 올바르게 작동 하도록 보장을 하는 네임 스페이스를 포함 하 여 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 콘솔 응용 프로그램 및 Windows Forms 응용 프로그램입니다. 이 구성 요소를 디자인할 수 이기도 한 <xref:System.Windows.Forms.PropertyGrid> 제어 및 사용자 고유의 사용자 지정 디자이너입니다.  
  
 을 통해 때 비동기적으로 소수를 계산 하는 응용 프로그램을 해야 합니다. 응용 프로그램은 각 소수 계산에 대 한 스레드 및 기본 사용자 인터페이스 (UI) 스레드를 갖습니다. 많은 수 인지를 테스트 하지만 prime 상당한 시간이 걸릴 수 있습니다, 이러한 지연에 의해 주 UI 스레드를 중단 되지 않습니다 하 고 계산 하는 동안 폼 응답 됩니다. 보류 중인 계산 취소 하 고 선택적으로 동시에 원하는 만큼 많은 계산을 실행할 수 없게 됩니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   구성 요소 만들기  
  
-   공용 비동기 이벤트 및 대리자 정의  
  
-   전용 대리자 정의  
  
-   Public 이벤트를 구현합니다.  
  
-   완료 메서드 구현  
  
-   작업자 메서드 구현  
  
-   시작 및 취소 메서드를 구현합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 이벤트 기반 비동기 패턴을 지 원하는 구성 요소를 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="creating-the-component"></a>구성 요소 만들기  
 첫 번째 단계는 이벤트 기반 비동기 패턴을 구현 하는 구성 요소를 만드는 것입니다.  
  
#### <a name="to-create-the-component"></a>구성 요소를 만들려면  
  
-   라는 클래스를 만들고 `PrimeNumberCalculator` 에서 상속 되는 <xref:System.ComponentModel.Component>합니다.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>공용 비동기 이벤트 및 대리자 정의  
 구성 요소 이벤트를 사용 하는 클라이언트와 통신 합니다. *MethodName* `Completed` 이벤트 경고는 비동기 작업을 완료 하는 클라이언트 및 *MethodName* `ProgressChanged` 이벤트는 비동기 작업의 진행률에 대 한 클라이언트에 알립니다.  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>클라이언트 구성 요소에 대 한 비동기 이벤트를 정의 합니다.  
  
1.  가져오기는 <xref:System.Threading?displayProperty=nameWithType> 및 <xref:System.Collections.Specialized?displayProperty=nameWithType> 파일의 위쪽에서 네임 스페이스입니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  전에 `PrimeNumberCalculator` 클래스 정의 진행률 및 완료 이벤트에 대 한 대리자를 선언 합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  에 `PrimeNumberCalculator` 클래스 정의 보고 진행률 및 완료를 클라이언트에 대 한 이벤트를 선언 합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  후의 `PrimeNumberCalculator` 클래스 정의 파생 시킵니다는 `CalculatePrimeCompletedEventArgs` 보고에 대 한 클라이언트의 이벤트 처리기에 각 계산의 결과 대 한 클래스는 `CalculatePrimeCompleted`시킵니다. 이외에 `AsyncCompletedEventArgs` 속성을이 클래스를 통해 클라이언트가 어떤 번호 테스트 됨, 소수 인지 여부 및 첫 번째 제 수 란 주요 하지 않은 경우를 결정 하도록 합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 구성 요소를 작성할 수 있습니다.  
  
#### <a name="to-test-your-component"></a>구성 요소를 테스트 하려면  
  
-   구성 요소를 컴파일하십시오.  
  
     두 개의 컴파일러 경고가 표시 됩니다.  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     다음 섹션에서 이러한 경고를 지웁니다.  
  
## <a name="defining-private-delegates"></a>전용 대리자 정의  
 비동기 측면에서 `PrimeNumberCalculator` 이라는 특별 한 대리자와 내부적으로 구현 되며 구성 요소는 <xref:System.Threading.SendOrPostCallback>합니다. A <xref:System.Threading.SendOrPostCallback> 에서 실행 되는 콜백 메서드를 나타내는 <xref:System.Threading.ThreadPool> 스레드입니다. 콜백 메서드에 형식의 단일 매개 변수를 사용 하는 서명이 있어야 합니다. <xref:System.Object>, 대리자에는 래퍼 클래스 간에 상태를 전달 해야 합니다 것입니다. 자세한 내용은 <xref:System.Threading.SendOrPostCallback>을 참조하십시오.  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>구성 요소의 내부 비동기 동작을 구현 합니다.  
  
1.  선언 하 고 생성 된 <xref:System.Threading.SendOrPostCallback> 에서 대리자는 `PrimeNumberCalculator` 클래스. 만들기는 <xref:System.Threading.SendOrPostCallback> 유틸리티 메서드에서 개체 라고 `InitializeDelegates`합니다.  
  
     두 명의 대리자 필요 합니다: 클라이언트에 진행률을 보고 및 클라이언트에 대 한 완료를 보고 합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  호출 된 `InitializeDelegates` 구성 요소의 생성자에서 메서드.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  대리자를 선언에서 `PrimeNumberCalculator` 비동기적으로 수행 해야 하는 실제 작업을 처리 하는 클래스입니다. 이 대리자에는 숫자가 소수 인지 여부를 테스트 하는 작업자 메서드로를 래핑합니다. 대리자를 사용는 <xref:System.ComponentModel.AsyncOperation> 매개 변수는 비동기 작업의 수명을 추적 하는 데 사용 됩니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  보류 중인 비동기 작업의 수명을 관리 하기 위한 컬렉션을 만듭니다. 클라이언트가 실행 되 고 완료 되 면 클라이언트에서 비동기 메서드를 호출할 때 고유한 토큰 또는 작업 ID를 전달 하는 클라이언트를 요구 하 여 수행 됩니다이 추적으로 작업을 추적 하는 방법이 필요 합니다. `PrimeNumberCalculator` 구성 요소 해야 한 추적 호출할 때마다 해당 호출을 작업 ID를 연결 하 여 합니다. 클라이언트에서는 고유 하지 않으면 작업 ID를 전달 하는 경우는 `PrimeNumberCalculator` 구성 요소에서 예외가 발생 합니다.  
  
     `PrimeNumberCalculator` 구성 요소는 추적 작업 ID 라는 특수 한 컬렉션 클래스를 사용 하 여는 <xref:System.Collections.Specialized.HybridDictionary>합니다. 만들 클래스 정의에 <xref:System.Collections.Specialized.HybridDictionary> 호출 `userTokenToLifetime`합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Public 이벤트를 구현합니다.  
 이벤트 기반 비동기 패턴을 구현 하는 구성 요소 이벤트를 사용 하는 클라이언트에 전달 합니다. 이러한 이벤트에 사용 하 여 적절 한 스레드에서 호출 되는 <xref:System.ComponentModel.AsyncOperation> 클래스입니다.  
  
#### <a name="to-raise-events-to-your-components-clients"></a>이벤트를 발생 시키는 구성 요소의 클라이언트:  
  
1.  클라이언트에 대 한 보고에 대 한 공용 이벤트를 구현 합니다. 진행률 및 완료를 보고에 대 한 보고에 대 한 이벤트에 필요 합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>완료 메서드 구현  
 완료 대리자는 성공적으로 완료, 오류 또는 취소 하 여 비동기 작업이 종료 될 때 원본으로 사용, 자유 스레드 비동기 동작에서 실행할 메서드입니다. 이 호출 임의의 스레드에서 발생합니다.  
  
 이 메서드는 클라이언트의 작업 ID 고유한 클라이언트 토큰의 내부 컬렉션에서 제거 되는 위치입니다. 이 메서드를 호출 하 여 특정 비동기 작업의 수명을 끝납니다는 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드 해당 <xref:System.ComponentModel.AsyncOperation>합니다. 이 호출 되는 응용 프로그램 모델에 대 한 적합 한 스레드에서 완료 이벤트를 발생 시킵니다. 이후에 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드가 호출 되 면이 인스턴스의 <xref:System.ComponentModel.AsyncOperation> 더 이상 사용할 수 및 모든 후속 사용 하려고 하면 예외가 throw 됩니다.  
  
 `CompletionMethod` 서명 비동기 작업의 결과 설명 하는 데 필요한 모든 상태를 보유 해야 합니다. 인지 수 및 해당 첫 번째 제 수 값 prime 숫자가 아닌 경우이 특정 비동기 작업에서 테스트 한 수에 대 한 상태를 저장 합니다. 발생 한 모든 예외를 설명 하는 상태 저장 및 <xref:System.ComponentModel.AsyncOperation> 이 특정 작업에 해당 합니다.  
  
#### <a name="to-complete-an-asynchronous-operation"></a>에 비동기 작업을 완료 합니다.  
  
-   완료 메서드를 구현 합니다. 걸리는 채우는 데 사용 하 여 6 개의 매개 변수는 `CalculatePrimeCompletedEventArgs` 클라이언트의를 통해 클라이언트에 반환 되는 `CalculatePrimeCompletedEventHandler`합니다. 내부 컬렉션에서 클라이언트의 작업 ID 토큰을 제거 하 고 호출 하 여 비동기 작업의 수명을 종료 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>합니다. <xref:System.ComponentModel.AsyncOperation> 스레드나 응용 프로그램 모델에 적합 한 컨텍스트에서에 대 한 호출을 마샬링합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 구성 요소를 작성할 수 있습니다.  
  
#### <a name="to-test-your-component"></a>구성 요소를 테스트 하려면  
  
-   구성 요소를 컴파일하십시오.  
  
     컴파일러 경고가 표시 됩니다.  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     다음 섹션에서이 경고가 해결 됩니다.  
  
## <a name="implementing-the-worker-methods"></a>작업자 메서드 구현  
 지금까지 지 원하는 비동기 코드에 대 한 구현한는 `PrimeNumberCalculator` 구성 요소입니다. 이제 실제 작업을 수행 하는 코드를 구현할 수 있습니다. 세 가지 메서드를 구현 합니다. `CalculateWorker`, `BuildPrimeNumberList`, 및 `IsPrime`합니다. 함께 `BuildPrimeNumberList` 및 `IsPrime` 는 에라토스테네스의 체 테스트 숫자의 제곱근까지 모든 소수를 검색 하 여 숫자 소수 인지를 결정 하는 호출 하는 잘 알려진 알고리즘을 구성 합니다. 자신과 없는에서 발견 되 면 숫자는 소수입니다.  
  
 이 구성 요소는 최대 효율성을 위해 작성 된 것을 다른 테스트 숫자에 대 한 다양 한 호출에서 검색 된 모든 주요 번호를 기억 합니다. 2, 3 및 5와 같은 단순한 제 있는지도 확인 합니다. 하지만이 예의 목적은 방법을 시간이 많이 걸리는 작업을 보여 주는 것 수 비동기적 실행 이러한 최적화를 연습으로 남아 있도록 합니다.  
  
 `CalculateWorker` 메서드는 대리자에 겹쳐서 표시 및에 대 한 호출을 사용 하 여 비동기적으로 호출 `BeginInvoke`합니다.  
  
> [!NOTE]
>  구현 되는 진행률 보고는 `BuildPrimeNumberList` 메서드. 빠른 컴퓨터 `ProgressChanged` 이벤트를 연속적으로 빠르게 발생할 수 있습니다. 에 이러한 이벤트가 발생 되 면 클라이언트 스레드가이 상황을 처리할 수 있어야 합니다. 사용자 인터페이스 코드 수 있습니다 메시지와 함께 서비스 장애 유발 하 고, 지속할 수 없습니다 동작을 중단 합니다. 이 상황을 처리 하는 예제 사용자 인터페이스에 대 한 참조 [하는 방법: 이벤트 기반 비동기 패턴의 클라이언트 구현](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)합니다.  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>에 소수 계산을 비동기적으로 실행 합니다.  
  
1.  구현 된 `TaskCanceled` 유틸리티 메서드. 이 메서드는 특정된 작업 ID에 대 한 작업 수명 컬렉션 확인 하 고 반환 `true` 경우 작업 ID를 찾을 수 없습니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  `CalculateWorker` 메서드를 구현합니다. 두 개의 매개 변수를 사용: 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  `BuildPrimeNumberList`를 구현해야 합니다. 두 개의 매개 변수를 사용: 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>합니다. 사용 하 여는 <xref:System.ComponentModel.AsyncOperation> 보고서 진행률 및 증분 결과를 합니다. 이렇게 하면 적절 한 스레드나 응용 프로그램 모델에 대 한 컨텍스트는 클라이언트의 이벤트 처리기가 호출 됩니다. 때 `BuildPrimeNumberList` 소수에서 찾은 것이 증분 결과로 보고에 대 한 클라이언트의 이벤트 처리기는 `ProgressChanged` 이벤트입니다. 파생 된 클래스가 필요 <xref:System.ComponentModel.ProgressChangedEventArgs>라는 `CalculatePrimeProgressChangedEventArgs`에 하나 추가할 라는 속성이 `LatestPrimeNumber`합니다.  
  
     `BuildPrimeNumberList` 메서드 호출도 정기적으로 `TaskCanceled` 메서드와 메서드가 반환 하는 경우 종료 되거나 `true`합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  `IsPrime`를 구현해야 합니다. 세 개의 매개 변수를 걸리는: 알려진된 소수, 테스트할 숫자 및 찾은 첫 번째 제수의 대 한 출력 매개 변수 목록입니다. 테스트 수가 소수 인지 결정 소수의 목록을 제공 합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  파생 `CalculatePrimeProgressChangedEventArgs` 에서 <xref:System.ComponentModel.ProgressChangedEventArgs>합니다. 이 클래스는 증분 결과 대 한 클라이언트의 이벤트 처리기를 보고 하는 데 필요한는 `ProgressChanged` 이벤트입니다. 라는 추가 속성이 하나에 `LatestPrimeNumber`합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 구성 요소를 작성할 수 있습니다.  
  
#### <a name="to-test-your-component"></a>구성 요소를 테스트 하려면  
  
-   구성 요소를 컴파일하십시오.  
  
     모든 작업을 쓰면은 시작 하 고 비동기 작업을 취소 방법 `CalculatePrimeAsync` 및 `CancelAsync`합니다.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>시작 및 취소 메서드를 구현합니다.  
 작업자 메서드를 호출 하 여 시작 자체 스레드에서 `BeginInvoke` 래핑하는 대리자에 있습니다. 호출 된 특정 비동기 작업의 수명을 관리 하기는 <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> 에서 메서드는 <xref:System.ComponentModel.AsyncOperationManager> 도우미 클래스입니다. 반환 합니다.는 <xref:System.ComponentModel.AsyncOperation>, 클라이언트의 이벤트 처리기 호출을 올바른 스레드 또는 컨텍스트로 마샬링하는 합니다.  
  
 호출 하 여 특정 한 보류 중인 작업을 취소 하면 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 하면 해당에 <xref:System.ComponentModel.AsyncOperation>합니다. 이렇게 호출 하 고, 해당 작업을 종료 해당 <xref:System.ComponentModel.AsyncOperation> 예외가 throw 됩니다.  
  
#### <a name="to-implement-start-and-cancel-functionality"></a>시작을 구현 하려면 및 취소 기능:  
  
1.  `CalculatePrimeAsync` 메서드를 구현합니다. 클라이언트에서 제공한 토큰 (작업 ID)가 현재 보류 중인 작업을 나타내는 모든 토큰에 대해 고유한 지 확인 합니다. 클라이언트 고유 하지 않은 토큰에 전달 하는 경우 `CalculatePrimeAsync` 예외를 발생 시킵니다. 그렇지 않으면 토큰 작업 ID 컬렉션에 추가 됩니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  `CancelAsync` 메서드를 구현합니다. 경우는 `taskId` 매개 변수가 토큰 컬렉션에 있는지에 제거 됩니다. 이렇게 하면 실행에서이 시작 되지 않은 취소 된 작업 수 없습니다. 작업이 실행 되는 경우는 `BuildPrimeNumberList` 메서드가 작업 ID 수명 컬렉션에서 제거 된 것을 발견 하면 종료 됩니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 구성 요소를 작성할 수 있습니다.  
  
#### <a name="to-test-your-component"></a>구성 요소를 테스트 하려면  
  
-   구성 요소를 컴파일하십시오.  
  
 `PrimeNumberCalculator` 구성 요소는 이제 완벽 하 고 사용할 준비가 됩니다.  
  
 사용 하는 예제 클라이언트는 `PrimeNumberCalculator` 구성 요소 참조 [하는 방법: 이벤트 기반 비동기 패턴의 클라이언트 구현](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 예제를 작성 하 여 채울 수 `CalculatePrime`, 해당 하는 동기 `CalculatePrimeAsync` 메서드. 이렇게 하면는 `PrimeNumberCalculator` 구성 요소는 이벤트 기반 비동기 패턴을 완벽 하 게 준수 합니다.  
  
 이 예제에서는 서로 다른 테스트 숫자에 대 한 다양 한 호출에서 검색 된 모든 주요 번호 목록을 유지 하 여 개선할 수 있습니다. 이 방법을 사용 하면 이전 태스크에서 수행 된 작업에서 각 태스크를 제공 합니다. 이 목록으로 보호 하 `lock` 영역, 하므로 다른 스레드에서 목록에 대 한 액세스는 직렬화 됩니다.  
  
 또한 2, 3 및 5와 같은 단순한 제, 테스트 하 여이 예제를 개선할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 백그라운드에서 작업 실행](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [빌드에 없음: Visual Basic의 다중 스레딩](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
