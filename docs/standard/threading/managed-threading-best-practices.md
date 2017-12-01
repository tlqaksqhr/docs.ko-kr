---
title: "관리되는 스레딩을 구현하는 최선의 방법"
ms.custom: 
ms.date: 11/30/2017
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
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e396bb1f6a710e49e311ca1526a7aae9bca7bf90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="managed-threading-best-practices"></a>관리되는 스레딩을 구현하는 최선의 방법
다중 스레딩에는 신중한 프로그래밍이 필요합니다. 대부분의 작업의 경우 스레드 풀 스레드로 실행에 대한 요청을 큐에 대기시켜 복잡성을 줄일 수 있습니다. 이 항목에서는 다중 스레드의 작업 조정 또는 차단되는 스레드 처리 등의 더욱 어려운 상황을 다룹니다.  
  
> [!NOTE]
> 작업 병렬 라이브러리 및 PLINQ의 일부 복잡성 및 다중 스레드 프로그래밍의 위험을 줄여주는 Api를 제공.NET Framework 4 부터는 합니다. 자세한 내용은 참조 [.NET의 병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)합니다.  
  
## <a name="deadlocks-and-race-conditions"></a>교착 상태 및 경합 상태  
 다중 스레딩은 처리량 및 응답성을 사용하여 문제를 해결하지만 이 과정에서 교착 상태 및 경합 상태의 새로운 문제를 유발합니다.  
  
### <a name="deadlocks"></a>교착 상태  
 교착 상태는 두 개의 각 스레드가 다른 스레드가 이미 잠근 리소스를 잠그려고 할 때 발생합니다. 두 스레드는 더 이상 진행할 수 없습니다.  
  
 관리되는 스레딩 클래스의 많은 메서드는 교착 상태를 감지하는 데 도움이 되는 시간 제한을 제공합니다. 다음 코드 예를 들어 라는 개체에 대 한 잠금을 획득 하려고 `lockObject`합니다. 그러면 300 밀리초에서 잠금을 가져오지 않은 경우 <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 반환 `false`합니다.  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a>경합 조건  
 경합 상태는 두 개 이상의 스레드에 의존하는 프로그램의 결과가 특정 코드 블록에 먼저 도달하는 경우에 발생하는 버그입니다. 프로그램을 여러 번 실행하면 서로 다른 결과를 생성하며 지정된 실행의 결과는 예측할 수 없습니다.  
  
 경합 상태의 간단한 예는 필드를 증가시키는 경우입니다. 클래스에 `objCt++;`(C#) 또는 `objCt += 1`(Visual Basic)과 같은 코드를 사용하는, 클래스의 인스턴스가 생성될 때마다 증가되는 개인 **정적** 필드(Visual Basic에서 **Shared**)가 있다고 가정합니다. 이 작업은 `objCt`에서 레지스터로 값을 로드하고, 값을 증가시키고 `objCt`에 저장해야 합니다.  
  
 다중 스레드 응용 프로그램에서 값을 로드하고 증가시킨 스레드는 세 단계 모두를 수행하는 다른 스레드에 의해 선점될 수 있습니다. 첫 번째 스레드가 실행을 다시 시작하고 해당 값을 저장할 때 그 사이에 값이 변경된 사실을 고려하지 않고 `objCt`를 덮어씁니다.  
  
 메서드를 사용 하 여이 특정 경합 상태를 쉽게 피할 수는 <xref:System.Threading.Interlocked> 클래스 같은 <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>합니다. 다중 스레딩 간에 데이터를 동기화하는 다른 기술에 대해 알아보려면 [다중 스레딩을 위한 데이터 동기화](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)를 참조하세요.  
  
 경합 상태는 다중 스레드의 작업을 동기화할 때에도 발생할 수 있습니다. 코드 줄을 작성할 때마다 줄을 실행하기 전에(또는 줄을 구성하는 개별 컴퓨터 명령 전에) 스레드가 선점되었고 다른 스레드가 먼저 사용한 경우 발생할 수 있는 상황을 고려해야 합니다.  
  
## <a name="number-of-processors"></a>프로세서 수  
 이제 대부분의 컴퓨터와 태블릿 및 휴대폰과 같은 소형 장치에도 다중 프로세서(코어라고도 함)가 있습니다. 단일 프로세서 컴퓨터에서도 실행되는 소프트웨어를 개발 중임을 아는 경우 다중 스레딩은 단일 프로세서 컴퓨터 및 다중 프로세서 컴퓨터에 대해 다른 문제를 해결한다는 것을 알아야 합니다.  
  
### <a name="multiprocessor-computers"></a>다중 프로세서 컴퓨터  
 다중 스레딩은 더 높은 처리량을 제공합니다. 10개의 프로세서는 한 개의 프로세서보다 10배의 작업을 수행할 수 있지만 모든 10개의 프로세서가 한 번에 작업할 수 있도록 작업이 나뉘어져 있는 경우에만 스레드는 작업을 나누고 추가 처리 능력을 활용하는 쉬운 방법을 제공합니다. 다중 프로세서 컴퓨터에서 다중 스레딩을 사용하는 경우:  
  
-   동시에 실행할 수 있는 스레드 수는 프로세서의 수로 제한됩니다.  
  
-   백그라운드 스레드는 포그라운드 스레드 실행 수가 프로세서 수보다 작은 경우에만 실행합니다.  
  
-   호출 하는 경우는 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> 스레드에서 메서드를 해당 스레드 수 또는 프로세서 수와 현재 실행 대기 중인 스레드 수에 따라 실행이 즉시 시작 되지 않을 수 있습니다.  
  
-   경합 상태는 스레드가 예기치 않게 선점되었기 때문에만 아니라 다른 프로세서에서 실행되는 두 개의 스레드가 동일한 코드 블록에 도달하기 위해 경쟁할 수 있기 때문에 발생할 수 있습니다.  
  
### <a name="single-processor-computers"></a>단일 프로세서 컴퓨터  
 다중 스레딩은 컴퓨터 사용자에게 큰 응답성을 제공하고 백그라운드 작업에 유휴 시간을 사용합니다. 단일 프로세서 컴퓨터에서 다중 스레딩을 사용하는 경우:  
  
-   어떠한 경우든 하나의 스레드만 실행합니다.  
  
-   백그라운드 스레드는 주 사용자 스레드가 유휴 상태일 때에만 실행합니다. 지속적으로 실행하는 포그라운드 스레드는 백그라운드 스레드의 프로세서 시간을 가져와서 사용합니다.  
  
-   호출 하는 경우는 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> 메서드 생성 되거나 운영 체제에 의해 선점 될 스레드가 현재 스레드가 될 때까지 실행을 시작 하지 않습니다 하는 스레드에서 합니다.  
  
-   경합 상태는 일반적으로 스레드가 가끔 다른 스레드가 코드 블록에 먼저 도달하도록 허용하는 곤란한 상황에서 선점될 수 있다는 사실을 프로그래머가 예측하지 않았기 때문에 발생합니다.  
  
## <a name="static-members-and-static-constructors"></a>정적 멤버 및 정적 생성자  
 클래스는 해당 클래스 생성자(C#에서 `static` 생성자, Visual Basic에서 `Shared Sub New`)가 실행을 완료할 때까지 초기화되지 않습니다. 초기화되지 않는 형식에서 코드의 실행을 방지하려면 공용 언어 런타임은 클래스 생성자가 실행을 완료할 때까지 다른 스레드에서 클래스의 `static` 멤버(Visual Basic에서 `Shared` 멤버)로 모든 호출을 차단합니다.  
  
 예를 들어 클래스 생성자가 새 스레드를 시작하고 스레드 프로시저가 클래스의 `static` 멤버를 호출하는 경우 새 스레드는 클래스 생성자가 완료할 때까지 차단됩니다.  
  
 이는 `static` 생성자를 가질 수 있는 모든 형식에 적용됩니다.  
  
## <a name="general-recommendations"></a>일반 권장 사항  
 다중 스레드를 사용하는 경우 다음 지침을 고려합니다.  
  
-   사용 하지 않는 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 다른 스레드를 종료 합니다. 다른 스레드에서 **Abort**를 호출하는 것은 해당 처리에서 해당 스레드가 어떤 지점에 도달했는지 알지 못하면서 해당 스레드에서 예외를 throw하는 것과 유사합니다.  
  
-   사용 하지 마십시오 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> 에 다중 스레드 작업을 동기화 합니다. 사용 마십시오 <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, 및 <xref:System.Threading.Monitor>합니다.  
  
-   기본 프로그램(예: 이벤트 사용)에서 작업자 스레드의 실행을 제어하지 마세요. 대신 작업자 스레드가 작업을 확보할 때까지 대기하고, 실행하고, 완료되면 프로그램의 다른 부분에 알릴 수 있도록 프로그램을 디자인합니다. 작업자 스레드가 차단되지 않는 경우 스레드 풀 스레드를 사용하는 것이 좋습니다. <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType>작업자 스레드 블록 수 있는 경우에 유용 합니다.  
  
-   잠금 개체로 형식을 사용하지 마세요. 즉, 같은 코드를 사용 하지 `lock(typeof(X))` C# 또는 `SyncLock(GetType(X))` Visual Basic의 경우 또는의 사용에 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> 와 <xref:System.Type> 개체입니다. 지정된 된 형식에는 하나의 인스턴스만 <xref:System.Type?displayProperty=nameWithType> 응용 프로그램 도메인입니다. 잠금을 사용하는 형식이 공용인 경우 개인 외의 코드는 잠금을 사용할 수 있으며 교착 상태가 발생합니다. 추가 문제는 [최선의 안정성 구현 방법](../../../docs/framework/performance/reliability-best-practices.md)을 참조하세요.  
  
-   인스턴스를 잠글 때 주의합니다(예: C#에서 `lock(this)` 또는 Visual Basic에서 `SyncLock(Me)`). 형식 외부의 응용 프로그램에 있는 다른 코드가 개체에서 잠금을 사용하는 경우 교착 상태가 발생할 수 있습니다.  
  
-   모니터링을 시작한 스레드가 모니터링 중에 있는 동안 예외가 발생한 경우에도 항상 해당 모니터링을 유지하는지 확인합니다. C# [잠금](~/docs/csharp/language-reference/keywords/lock-statement.md) 문과 Visual Basic [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md) 문에서 제공이 동작은 자동으로 적용 하는 방법 한 **마지막** 되도록 블록 <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> 은 호출 됩니다. **Exit**이 호출될지 확인할 수 없는 경우 **뮤텍스**를 사용하도록 설계를 변경하는 것이 좋습니다. 뮤텍스는 현재 소유하고 있는 스레드가 종료되면 자동으로 해제됩니다.  
  
-   다른 리소스를 필요로 하는 작업에 대해 다중 스레드를 사용하고 단일 리소스에 다중 스레드를 할당하지 마세요. 예를 들어 해당 스레드는 I/O 작업 중에 차단되어 다른 스레드의 실행을 허용하므로 I/O와 관련된 모든 작업은 자체 스레드를 소유함으로써 이익을 얻습니다. 사용자 입력은 전용 스레드를 활용하는 다른 리소스입니다. 단일 프로세서 컴퓨터에서 집중적 계산을 포함하는 작업은 사용자 입력 및 I/O와 관련된 작업과 공존하지만 여러 계산 집약적인 작업은 서로 경쟁합니다.  
  
-   메서드를 사용 하는 것이 좋습니다는 <xref:System.Threading.Interlocked> 사용 하는 대신 간단한 상태 변경에 대 한 클래스는 `lock` 문 (`SyncLock` Visual basic에서). `lock` 문에 범용에 적합 한 도구 이지만 <xref:System.Threading.Interlocked> 클래스 원자 단위로 수행 되어야 하는 업데이트에 대 한 더 나은 성능을 제공 합니다. 경합이 없는 경우 내부적으로 단일 잠금 접두사를 실행합니다. 코드 검토에서 다음 예제에서와 같은 코드를 감시합니다. 첫 번째 예제에서 상태 변수가 증가됩니다.  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)   
    {  
        myField++;  
    }  
    ```  
  
     사용 하 여 성능을 향상 시킬 수 있습니다는 <xref:System.Threading.Interlocked.Increment%2A> 메서드 대신는 `lock` 문을 다음과 같이 합니다.  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    >  .NET Framework 버전 2.0에에서는 <xref:System.Threading.Interlocked.Add%2A> 메서드는 1 보다 큰 간격으로 자동 업데이트를 제공 합니다.  
  
     두 번째 예제에서 참조 형식 변수는 null 참조인 경우에만 업데이트됩니다(Visual Basic에서 `Nothing`).  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            if (x == null)  
            {  
                x = y;  
            }  
        }  
    }  
    ```  
  
     사용 하 여 성능을 향상 시킬 수는 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드 대신, 다음과 같습니다.  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    >  .NET Framework 버전 2.0에에서는 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드에 참조 형식의 형식 안전 하 게 대체에 사용할 수 있는 제네릭 오버 로드 합니다.  
  
## <a name="recommendations-for-class-libraries"></a>클래스 라이브러리에 대한 권장 사항  
 다중 스레딩에 대한 클래스 라이브러리를 설계할 때 다음 지침을 고려합니다.  
  
-   가능한 경우 동기화의 필요성을 피합니다. 많이 사용되는 코드의 경우 특히 그렇습니다. 예를 들어 경합 상태를 제거하는 대신 허용하도록 알고리즘을 조정할 수 있습니다. 불필요한 동기화는 성능을 저하시키고 교착 상태 및 경합 상태의 가능성을 만듭니다.  
  
-   기본적으로 정적 데이터(Visual Basic에서 `Shared`)를 스레드로부터 안전하게 만듭니다.  
  
-   기본적으로 인스턴스 데이터를 스레드로부터 안전하게 만들지 마세요. 스레드로부터 안전한 코드를 만드는 잠금을 추가하면 성능을 저하시키고 잠금 경합이 증가하고 교착 상태가 발생할 가능성을 만듭니다. 공용 응용 프로그램 모델에서 한 번에 하나의 스레드만이 스레드 보안의 필요성을 최소화하는 사용자 코드를 실행합니다. 이러한 이유로 .NET Framework 클래스 라이브러리는 기본적으로 스레드로부터 안전하지 않습니다.  
  
-   정적 상태를 변경하는 정적 메서드를 제공 하지 마세요. 일반적인 서버 시나리오에서 정적 상태는 요청 간 공유되며 여러 스레드가 동시에 해당 코드를 실행할 수 있음을 의미합니다. 스레드 버그가 발생할 가능성을 엽니다. 요청 간에 공유되지 않는 인스턴스로 데이터를 캡슐화하는 디자인 패턴을 사용하는 것이 좋습니다. 또한 정적 데이터가 동기화되는 경우 상태를 변경하는 정적 메서드 간 호출은 성능에 부정적인 영향을 주어 교착 상태 또는 중복된 동기화를 발생시킬 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레드 및 스레딩](../../../docs/standard/threading/threads-and-threading.md)
