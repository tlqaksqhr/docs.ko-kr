---
title: "Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern | Microsoft Docs"
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
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern
상당한 지연을 일으킬 수 있는 작업이 포함된 클래스를 쓸 경우 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)를 구현하여 비동기 기능을 주는 것이 좋습니다.  
  
 이 연습에서는 이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 설명합니다.  이 구성 요소는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 콘솔 응용 프로그램 및 Windows Forms 응용 프로그램을 비롯한 모든 응용 프로그램 모델에서 제대로 작동할 수 있도록 <xref:System.ComponentModel?displayProperty=fullName> 네임스페이스의 도우미 클래스를 사용하여 구현됩니다.  또한 이 구성 요소는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤과 자신만의 사용자 지정 디자이너를 사용하여 디자인할 수 있습니다.  
  
 이 연습을 마치면 소수를 비동기적으로 계산하는 응용 프로그램이 만들어집니다.  이 응용 프로그램에는 주 UI\(사용자 인터페이스\) 스레드와 각 소수 계산을 위한 스레드가 있습니다.  큰 수에 대하여 소수인지 여부를 테스트하려면 상당한 시간이 걸릴 수 있지만 이러한 시간 지연 때문에 주 UI 스레드가 중단되지는 않으며 계산 중에도 폼에서 응답할 수 있습니다.  여러 계산을 동시에 실행할 수 있으며 보류 중인 계산을 선택적으로 취소할 수 있습니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   구성 요소 만들기  
  
-   공용 비동기 이벤트 및 대리자 정의  
  
-   전용 대리자 정의  
  
-   공용 이벤트 구현  
  
-   완료 메서드 구현  
  
-   작업자 메서드 구현  
  
-   시작 및 취소 메서드 구현  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)을 참조하십시오.  
  
## 구성 요소 만들기  
 첫 번째 단계는 이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 것입니다.  
  
#### 구성 요소를 만들려면  
  
-   <xref:System.ComponentModel.Component>에서 상속되는 `PrimeNumberCalculator`라는 클래스를 만듭니다.  
  
## 공용 비동기 이벤트 및 대리자 정의  
 구성 요소는 이벤트를 사용하여 클라이언트와 통신합니다.  *MethodName*`Completed` 이벤트는 클라이언트에 비동기 작업의 완료를 알리고 *MethodName*`ProgressChanged` 이벤트는 클라이언트에 비동기 작업의 진행률을 알립니다.  
  
#### 구성 요소에 대한 클라이언트의 비동기 이벤트를 정의하려면  
  
1.  파일 맨 위에 <xref:System.Threading?displayProperty=fullName> 및 <xref:System.Collections.Specialized?displayProperty=fullName> 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  `PrimeNumberCalculator`  클래스 정의 앞에 진행 및 완료 이벤트에 대해 대리자를 선언합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  `PrimeNumberCalculator`  클래스 정의에서 진행 및 완료를 클라이언트에 보고하는 이벤트를 선언합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  `PrimeNumberCalculator`  클래스 정의 뒤에 `CalculatePrimeCompleted` 이벤트에 대한 클라이언트 이벤트 처리기에 각 계산의 결과를 보고하는  `CalculatePrimeCompletedEventArgs`  클래스를 파생시킵니다.  `AsyncCompletedEventArgs` 속성과 함께 이 클래스를 사용하여 클라이언트에서 테스트된 숫자, 이 숫자가 소수인지 여부 및 소수가 아닌 경우 첫째 제수가 무엇인지를 확인할 수 있습니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## 검사점  
 이 시점에서 구성 요소를 빌드합니다.  
  
#### 구성 요소를 테스트하려면  
  
-   구성 요소를 컴파일합니다.  
  
     다음과 같은 두 개의 컴파일러 경고가 발생합니다.  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     이 경고는 다음 섹션에서 지워집니다.  
  
## 전용 대리자 정의  
 `PrimeNumberCalculator` 구성 요소의 비동기 기능은 <xref:System.Threading.SendOrPostCallback>이라는 특수 대리자로 내부적으로 구현됩니다.  <xref:System.Threading.SendOrPostCallback>은 <xref:System.Threading.ThreadPool> 스레드에서 실행되는 콜백 메서드를 나타냅니다.  콜백 메서드에는 <xref:System.Object> 형식의 단일 매개 변수를 사용하는 시그니처가 있어야 합니다. 즉, 래퍼 클래스의 대리자 간에 상태 정보를 전달해야 합니다.  자세한 내용은 <xref:System.Threading.SendOrPostCallback>을 참조하십시오.  
  
#### 구성 요소의 내부 비동기 동작을 구현하려면  
  
1.  `PrimeNumberCalculator`  클래스에서  <xref:System.Threading.SendOrPostCallback> 대리자를 선언하고 만듭니다.   `InitializeDelegates`.라는 유틸리티 메서드에서 <xref:System.Threading.SendOrPostCallback> objects 개체를 만듭니다.  
  
     두 개의 대리자가 필요합니다. 하나는 클라이언트에 진행률을 보고하기 위한 것이고 다른 하나는 클라이언트에 완료를 보고하기 위한 것입니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  구성 요소의 생성자에서 `InitializeDelegates` 메서드를 호출합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  비동기적으로 수행될 실제 작업을 처리하는 `PrimeNumberCalculator` 클래스에서 대리자를 선언합니다.  이 대리자는 숫자가 소수인지 여부를 테스트하는 작업자 메서드를 래핑합니다.  대리자는 비동기 작업의 수명을 추적하는 데 사용되는 <xref:System.ComponentModel.AsyncOperation> 매개 변수를 사용합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  보류 중인 비동기 작업의 수명을 관리하는 컬렉션을 만듭니다.  클라이언트에는 작업이 실행되거나 완료될 때 이를 추적하는 방법이 필요하며, 이러한 추적은 클라이언트에서 비동기 메서드를 호출할 때 고유한 토큰이나 작업 ID를 전달하도록 클라이언트에 요청하여 수행됩니다.  `PrimeNumberCalculator` 구성 요소는 작업 ID와 해당 호출을 연결하여 각 호출을 추적해야 합니다.  클라이언트가 고유하지 않은 작업 ID를 전달하는 경우 `PrimeNumberCalculator` 구성 요소에서 예외를 발생시켜야 합니다.  
  
     `PrimeNumberCalculator` 구성 요소는 <xref:System.Collections.Specialized.HybridDictionary>라는 특수 컬렉션 클래스를 사용하여 작업 ID를 추적합니다.  클래스 정의에서  `userTokenToLifetime`이라는 <xref:System.Collections.Specialized.HybridDictionary>를 만듭니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## 공용 이벤트 구현  
 이벤트 기반 비동기 패턴을 구현하는 구성 요소는 이벤트를 사용하여 클라이언트와 통신합니다.  이러한 이벤트는 적절한 스레드에서 <xref:System.ComponentModel.AsyncOperation> 클래스를 통해 호출됩니다.  
  
#### 구성 요소 클라이언트에 이벤트를 발생시키려면  
  
1.  클라이언트에 보고하는 공용 이벤트를 구현합니다.  진행률을 보고하는 이벤트와 완료를 보고하는 이벤트가 필요합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## 완료 메서드 구현  
 완료 대리자는 성공적인 완료, 오류 또는 취소로 비동기 작업이 끝날 때 자유 스레드된 내부 비동기 동작이 호출하는 메서드입니다.  이 호출은 임의의 스레드에서 발생합니다.  
  
 이 메서드를 통해 클라이언트의 작업 ID가 고유한 클라이언트 토큰의 내부 컬렉션에서 제거됩니다.  또한 이 메서드는 해당하는 <xref:System.ComponentModel.AsyncOperation>의 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드를 호출하여 특정 비동기 작업의 수명을 끝냅니다.  이 호출은 응용 프로그램 모델에 적합한 스레드에서 완료 이벤트를 발생시킵니다.  <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> 메서드가 호출된 후에는 이 <xref:System.ComponentModel.AsyncOperation> 인스턴스를 더 이상 사용할 수 없으며 이후에 사용하려고 하면 예외가 throw됩니다.  
  
 `CompletionMethod` 시그니처는 비동기 작업의 결과를 설명하는 데 필요한 모든 상태를 보유해야 합니다.  이 클래스는 특정 비동기 작업에서 테스트한 숫자, 이 숫자가 소수인지 여부 및 소수가 아닌 경우 첫째 제수의 값에 대한 상태를 보유합니다.  또한 발생한 예외와 이 특정 작업에 해당하는 <xref:System.ComponentModel.AsyncOperation>을 설명하는 상태를 보유합니다.  
  
#### 비동기 작업을 완료하려면  
  
-   완료 메서드를 구현합니다.  이 메서드는 6개의 매개 변수를 사용하여 클라이언트의  `CalculatePrimeCompletedEventHandler` 를 통해 클라이언트에 반환되는  `CalculatePrimeCompletedEventArgs`를 채웁니다.  이 메서드는 내부 컬렉션에서 클라이언트의 작업 ID를 제거하고 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>를 호출하여 비동기 작업의 수명을 끝냅니다.  <xref:System.ComponentModel.AsyncOperation>은 응용 프로그램 모델에 적합한 스레드나 컨텍스트로 호출을 마샬링합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## 검사점  
 이 시점에서 구성 요소를 빌드합니다.  
  
#### 구성 요소를 테스트하려면  
  
-   구성 요소를 컴파일합니다.  
  
     다음과 같은 컴파일러 경고가 발생합니다.  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     이 경고는 다음 섹션에서 해결됩니다.  
  
## 작업자 메서드 구현  
 지금까지 `PrimeNumberCalculator` 구성 요소를 지원하는 비동기 코드를 구현했습니다.  이제 실제 작업을 하는 코드를 구현할 수 있습니다.  `CalculateWorker`, `BuildPrimeNumberList` 및 `IsPrime`의 세 가지 메서드를 구현합니다.  `BuildPrimeNumberList`와 `IsPrime`은 에라토스테네스의 체라는 잘 알려진 알고리즘을 구성합니다. 이 알고리즘은 테스트 대상 숫자의 제곱근에 이르기까지 모든 소수를 찾아서 숫자가 소수인지를 확인합니다.  제곱근에 이르기까지 제수가 없으면 그 숫자는 소수입니다.  
  
 이 구성 요소가 효율성을 최대화하도록 작성된 경우에는 서로 다른 테스트 숫자에 대한 다양한 호출을 통하여 발견되는 모든 소수를 기억합니다.  또한 2, 3, 5와 같은 단순한 제수도 확인합니다.  그러나 이 예제는 시간이 많이 걸리는 작업을 비동기적으로 실행하는 방법을 보여 주기 위한 것이므로 이러한 최적화는 다루지 않습니다.  
  
 `CalculateWorker` 메서드는 대리자에 래핑되고 `BeginInvoke` 호출과는 비동기적으로 호출됩니다.  
  
> [!NOTE]
>  진행률 보고는 `BuildPrimeNumberList` 메서드에서 구현됩니다.  빠른 컴퓨터에서는 `ProgressChanged` 이벤트가 연속해서 빠르게 발생할 수 있습니다.  이러한 이벤트가 발생하는 클라이언트 스레드에서는 이 상황을 처리할 수 있어야 합니다.  사용자 인터페이스 코드에서 메시지가 많이 발생하여 제때 처리하지 못하면 작동이 중지될 수 있습니다.  이 상환을 처리하는 예제 사용자 인터페이스는 [How to: Implement a Client of the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)을 참조하십시오.  
  
#### 소수 계산을 비동기적으로 실행하려면  
  
1.  `TaskCanceled` 유틸리티 메서드를 구현합니다.  이 메서드는 특정 작업 ID의 작업 수명 컬렉션을 확인하고 작업 ID가 없으면 `true`를 반환합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  `CalculateWorker` 메서드를 구현합니다.  이 메서드는 두 개의 매개 변수, 즉 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>을 사용합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  `BuildPrimeNumberList`를 구현합니다.  이 메서드는 두 개의 매개 변수, 즉 테스트할 숫자 및 <xref:System.ComponentModel.AsyncOperation>을 사용합니다.  또한 <xref:System.ComponentModel.AsyncOperation>을 사용하여 진행률과 증분 결과를 보고합니다.  이를 통해 클라이언트의 이벤트 처리기가 응용 프로그램 모델에 적합한 스레드나 컨텍스트에서 호출됩니다.  `BuildPrimeNumberList`에서 소수를 찾으면 이를 `ProgressChanged` 이벤트의 클라이언트 이벤트 처리기에 증분 결과로 보고합니다.  이때 <xref:System.ComponentModel.ProgressChangedEventArgs>에서 파생된 `CalculatePrimeProgressChangedEventArgs` 클래스가 필요합니다. 이 클래스에는 `LatestPrimeNumber`라는 추가 속성이 하나 있습니다.  
  
     또한 `BuildPrimeNumberList` 메서드는 정기적으로 `TaskCanceled` 메서드를 호출하며 이 메서드가 `true`를 반환하면 종료됩니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  `IsPrime`을 구현합니다.  이 메서드는 세 개의 매개 변수, 즉 알려진 소수 목록, 테스트할 숫자, 첫번째로 찾은 제수의 출력 매개 변수를 사용합니다.  소수 목록이 지정되면 이 메서드는 테스트 숫자가 소수인지 확인합니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  <xref:System.ComponentModel.ProgressChangedEventArgs>에서 `CalculatePrimeProgressChangedEventArgs`를 파생시킵니다.  이 클래스는 `ProgressChanged` 이벤트의 클라이언트 이벤트 처리기에 증분 결과를 보고하는 데 필요합니다.  이 클래스에는 `LatestPrimeNumber`라는 추가 속성이 하나 있습니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## 검사점  
 이 시점에서 구성 요소를 빌드합니다.  
  
#### 구성 요소를 테스트하려면  
  
-   구성 요소를 컴파일합니다.  
  
     이제 비동기 작업을 시작하거나 취소하는 `CalculatePrimeAsync` 및 `CancelAsync` 메서드만 쓰면 됩니다.  
  
## 시작 및 취소 메서드 구현  
 래핑하는 대리자의 `BeginInvoke`를 호출하여 작업자 메서드를 자체 스레드에서 시작합니다.  특정 비동기 작업의 수명을 관리하려면 <xref:System.ComponentModel.AsyncOperationManager> 도우미 클래스의 <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> 메서드를 호출합니다.  이 메서드는 클라이언트 이벤트 처리기 호출을 적절한 스레드나 컨텍스트로 마샬링하는 <xref:System.ComponentModel.AsyncOperation>을 반환합니다.  
  
 보류 중인 특정 작업을 취소하려면 해당하는 <xref:System.ComponentModel.AsyncOperation>의 <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>를 호출합니다.  이렇게 하면 해당 작업이 끝나고 이후에 <xref:System.ComponentModel.AsyncOperation>을 호출하는 경우 예외가 throw됩니다.  
  
#### 시작 및 취소 기능을 구현하려면  
  
1.  `CalculatePrimeAsync` 메서드를 구현합니다.  클라이언트 제공 토큰\(작업 ID\)이 현재 보류 중인 작업을 나타내는 모든 토큰에 대해 고유한지 확인합니다.  클라이언트에서 고유하지 않은 토큰을 전달하면 `CalculatePrimeAsync`에서 예외를 발생시킵니다.  그렇지 않으면 토큰이 작업 ID 컬렉션에 추가됩니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  `CancelAsync` 메서드를 구현합니다.  토큰 컬렉션에 `taskId` 매개 변수가 있으면 제거됩니다.  따라서 시작되지 않고 취소된 작업은 실행되지 않게 됩니다.  작업이 실행되고 있으면 `BuildPrimeNumberList` 메서드는 해당 작업 ID가 수명 컬렉션에서 제거되었음을 감지할 때 종료됩니다.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## 검사점  
 이 시점에서 구성 요소를 빌드합니다.  
  
#### 구성 요소를 테스트하려면  
  
-   구성 요소를 컴파일합니다.  
  
 이제  `PrimeNumberCalculator`  구성 요소가 완료되어 사용할 준비가 되었습니다.  
  
 `PrimeNumberCalculator` 구성 요소를 사용하는 클라이언트 예제를 보려면 [How to: Implement a Client of the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)을 참조하십시오.  
  
## 다음 단계  
 `CalculatePrimeAsync` 메서드와 동일한 동기 메서드인 `CalculatePrime`을 써서 이 예제에 추가할 수 있습니다.  이렇게 하면 `PrimeNumberCalculator` 구성 요소가 이벤트 기반 비동기 패턴과 완전히 호환됩니다.  
  
 여러 테스트 숫자에 대한 다양한 호출에서 발견된 모든 소수 목록을 유지하여 이 예제를 개선할 수 있습니다.  이 방법을 사용하면 각 작업에서 이전 작업의 결과를 활용할 수 있게 됩니다.  이 목록을 `lock` 영역으로 보호하여 목록에 대한 다른 스레드의 액세스가 serialize되게 합니다.  
  
 또한 2, 3, 5와 같이 간단한 제수를 대상으로 테스트하여 이 예제를 개선할 수 있습니다.  
  
## 참고 항목  
 [방법: 백그라운드에서 작업 실행](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/ko-kr/c731a50c-09c1-4468-9646-54c86b75d269)   
 [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)