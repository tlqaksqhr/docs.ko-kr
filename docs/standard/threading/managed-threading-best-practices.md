---
title: "Managed Threading Best Practices | Microsoft Docs"
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
  - "threading [.NET Framework], design guidelines"
  - "threading [.NET Framework], best practices"
  - "managed threading"
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Managed Threading Best Practices
다중 스레딩을 구현할 때는 주의해서 프로그래밍을 수행해야 합니다.  대부분의 작업에서는 요청을 대기시켜서 스레드 풀 스레드에서 실행되도록 하면 복잡성을 줄일 수 있습니다.  이 항목에서는 다중 스레드 작업의 조정, 다른 스레드의 실행을 차단하는 스레드의 처리 등 좀 더 어려운 상황을 해결하기 위한 내용을 다룹니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 작업 병렬 라이브러리 및 PLINQ를 통해 다중 스레드 프로그래밍의 일부 복잡성과 위험을 줄여주는 API를 제공합니다.  자세한 내용은 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)을 참조하십시오.  
  
## 교착 상태 및 경쟁 상태  
 다중 스레딩은 처리량과 반응성을 향상시켜 주지만 이 과정에서 교착 상태나 경쟁 상태와 같은 새로운 문제를 유발합니다.  
  
### 교착 상태  
 두 스레드 중 한 스레드가 이미 잠근 리소스를 나머지 스레드가 잠그려고 하면 교착 상태가 발생합니다.  두 스레드 모두 더 이상 실행될 수 없게 됩니다.  
  
 관리되는 스레딩 클래스의 많은 메서드는 교착 상태의 감지에 도움이 되는 제한 시간 기능을 제공합니다.  예를 들어, 다음 코드는 현재 인스턴스에 대해 잠금을 확보하려고 합니다.  300밀리초 안에 잠금을 확보하지 못하면<xref:System.Threading.Monitor.TryEnter%2A?displayProperty=fullName>는 **false**를 반환합니다.  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(Me)  
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
        Monitor.Exit(this);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### 경쟁 상태  
 경쟁 상태는 프로그램의 출력이 둘 이상의 스레드 중에서 어떤 스레드가 먼저 특정 코드 블록에 도달하는가에 따라 달라지는 경우에 발생하는 버그입니다.  이 프로그램을 여러 번 실행하면 매번 다른 결과가 생성되며 특정 실행의 결과를 예측할 수 없습니다.  
  
 경쟁 상태의 간단한 예로 필드를 증가시키는 경우를 들 수 있습니다.  클래스에 클래스 인스턴스가 만들어질 때마다 증가되는 전용 **static** 필드\(Visual Basic의 경우 **Shared**\)가 있으며 `objCt++;`\(C\#\) 또는 `objCt += 1`\(Visual Basic\)과 같은 코드를 사용한다고 가정합니다.  이 작업을 위해서는 `objCt`에서 레지스터로 값을 로드하고, 값을 증가시킨 후 `objCt`에 저장하는 과정이 필요합니다.  
  
 다중 스레드 응용 프로그램에서, 값을 로드하고 증가시킨 스레드는 세 가지 작업을 모두 수행하는 다른 스레드에 의해 선점될 수 있습니다. 즉, 첫 번째 스레드가 실행을 다시 시작하고 값을 저장할 때 다른 스레드는 해당 값이 일시적으로 변경되었다는 사실을 고려할 필요 없이 `objCt`를 덮어씁니다.  
  
 이러한 특수한 경쟁 상태는 <xref:System.Threading.Interlocked.Increment%2A?displayProperty=fullName>와 같은 <xref:System.Threading.Interlocked> 클래스의 메서드를 사용하면 쉽게 방지할 수 있습니다.  다중 스레드 간에 데이터를 동기화하기 위한 다른 방법에 대해서는 [다중 스레딩을 위한 데이터 동기화](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)를 참조하십시오.  
  
 경쟁 상태는 다중 스레드의 작업을 동기화할 때도 발생할 수 있습니다.  코드를 작성할 때마다 해당 줄을 실행하기 전에 또는 해당 줄을 구성하는 개별적인 컴퓨터 명령을 실행하기 전에 스레드가 선점되고 다른 스레드가 먼저 실행될 경우 어떤 결과가 나타날 수 있는지 고려해야 합니다.  
  
## 프로세서 개수  
 대부분의 컴퓨터는 이제 태블릿과 전화기와 같은 작은 장치에도 다중 프로세서\(코어라고도 함\)를 사용하고 있습니다.  또한 단일 프로세서 컴퓨터에서도 실행될 소프트웨어를 알고 개발하는 경우 멀티 스레드로 단일 프로세서 컴퓨터와 멀티 프로세서 컴퓨터의 다른 문제가 해결된다는 것을 알아야 합니다.  
  
### 다중 프로세서 컴퓨터  
 다중 스레딩을 사용하면 처리량이 크게 향상됩니다.  10개의 프로세서는 하나의 프로세서로 수행할 수 있는 작업의 10배를 처리할 수 있지만 10개의 프로세서가 모두 작동될 수 있도록 작업이 나뉘어져 있을 때만 가능합니다. 스레드 기능은 작업을 쉽게 나누어 여분의 처리 능력을 활용할 수 있도록 해줍니다.  다중 프로세서 컴퓨터에서 다중 스레딩을 사용할 경우 다음 현상이 나타납니다.  
  
-   동시에 실행될 수 있는 스레드 수가 프로세서 수에 의해 제한됩니다.  
  
-   백그라운드 스레드는 실행되는 포그라운드 스레드 수가 프로세서 수보다 작을 때만 실행됩니다.  
  
-   스레드에 대해 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> 메서드를 호출하면 해당 스레드는 프로세서 수와 현재 실행을 기다리는 스레드 수에 따라 실행이 즉시 시작될 수도 있고 그렇지 않을 수도 있습니다.  
  
-   스레드가 예기치 못하게 선점되었기 때문에 그리고 여러 다른 프로세스에서 실행되는 두 개의 스레드가 동일한 코드 블록에 도달하기 위해 경쟁하기 때문에 경쟁 상태가 발생할 수 있습니다.  
  
### 단일 프로세서 컴퓨터  
 다중 스레딩은 컴퓨터 사용자에게 보다 빠른 응답 능력을 제공하며 유휴 시간에 백그라운드 작업을 처리합니다.  단일 프로세서 컴퓨터에서 다중 스레딩을 사용할 경우 다음 현상이 나타납니다.  
  
-   언제나 스레드가 하나만 실행됩니다.  
  
-   백그라운드 스레드는 주 사용자 스레드가 유휴 상태일 때만 실행됩니다.  계속 실행되는 포그라운드 스레드는 백그라운드 스레드의 프로세서 시간을 가져와서 사용합니다.  
  
-   스레드에 대해 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> 메서드를 호출하면 해당 스레드는 현재 스레드가 운영 체제로 양도되거나 선점될 때까지 실행을 시작하지 않습니다.  
  
-   경쟁 상태는 일반적으로 복잡한 상황에서 스레드가 선점될 수 있다는 사실을 프로그래머가 예측하지 못하여 다른 스레드가 먼저 코드 블록에 도달할 수 있기 때문에 발생합니다.  
  
## 정적 멤버 및 정적 생성자  
 클래스는 클래스 생성자\(C\#의 `static` 생성자, Visual Basic의 `Shared Sub New`\)의 실행이 완료되어야 초기화됩니다.  초기화되지 않은 형식에서 코드가 실행되지 않도록 하기 위해 공용 언어 런타임에서는 클래스 생성자의 실행이 완료될 때까지 다른 스레드에서 해당 클래스의 모든 `static` 멤버\(Visual Basic의 경우 `Shared` 멤버\)를 호출하지 못하도록 차단합니다.  
  
 예를 들어, 클래스 생성자가 새 스레드를 시작하면 스레드 프로시저는 해당 클래스의 `static` 멤버를 호출하고 새 스레드는 클래스 생성자가 완료될 때까지 차단됩니다.  
  
 이는 `static` 생성자가 있는 모든 형식에 적용됩니다.  
  
## 일반 권장 사항  
 다중 스레드를 사용할 때 다음 지침을 고려하십시오.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>를 사용하여 다른 스레드를 종료하지 않습니다.  다른 스레드에 대해 **Abort**를 호출하는 것은 해당 스레드가 처리 과정 중 어떤 지점에 도달했는지 알지 못하는 상태에서 해당 스레드에 대해 예외를 throw하는 것과 유사한 결과를 가져옵니다.  
  
-   다중 스레드의 작업을 동기화하는 데 <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> 메서드를 사용하지 않습니다.  대신 <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.Monitor>를 사용합니다.  
  
-   기본 프로그램에서 작업자 스레드의 실행을 제어하지 않습니다\(예: 이벤트 사용\).  대신 작업을 사용할 수 있을 때까지 작업자 스레드가 대기했다가 작업을 실행하고 작업이 끝나면 프로그램의 다른 부분에 알릴 수 있게 프로그램을 설계합니다.  작업자 스레드의 실행이 차단되면 스레드 풀의 스레드를 사용하는 것을 고려합니다.  작업자 스레드의 실행이 차단되는 경우에는 <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=fullName>이 유용합니다.  
  
-   형식을 잠금 개체로 사용하지 마십시오.  즉, C\#의 `lock(typeof(X))` 또는 Visual Basic의`SyncLock(GetType(X))`과 같은 코드를 사용하거나 <xref:System.Type> 개체와 함께 <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName>를 사용하지 마십시오.  특정 형식에 대해 <xref:System.Type?displayProperty=fullName> 인스턴스는 각 응용 프로그램 도메인마다 하나씩만 있습니다.  잠그는 형식이 공용 형식이면 다른 코드에서 해당 형식을 잠글 수 있으며 이 경우 교착 상태가 발생합니다.  추가 문제는 [최선의 안정성 구현 방법](../../../docs/framework/performance/reliability-best-practices.md)을 참조하십시오.  
  
-   C\#의 `lock(this)` 또는 Visual Basic의 `SyncLock(Me)`과 같은 코드로 인스턴스를 잠글 때는 주의해야 합니다.  응용 프로그램의 다른 코드, 즉 해당 형식의 외부 코드에서 해당 개체를 잠그면 교착 상태가 발생할 수 있습니다.  
  
-   스레드가 모니터 상에 있는 동안 예외가 발생하는 경우에도 모니터에 들어간 스레드가 항상 해당 모니터를 떠나도록 합니다.  C\# [lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md) 문과 Visual Basic [SyncLock](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md) 문은 이 동작을 자동으로 제공하며 **finally** 블록을 사용하여 <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName>가 호출되도록 합니다.  **Exit**가 호출될지 확신할 수 없으면 **Mutex**를 사용하도록 설계를 변경할 수 있습니다.  현재 뮤텍스를 소유하는 스레드가 종료될 때 뮤텍스는 자동으로 해제됩니다.  
  
-   여러 다른 리소스를 필요로 하는 작업에 대해 다중 리소스를 사용하고 여러 스레드를 단일 리소스에 할당하지 않도록 합니다.  예를 들어, 해당 스레드는 작업 중에 차단되므로 다른 스레드가 실행될 수 있기 때문에 I\/O과 연관된 모든 작업은 자체의 스레드를 가질 경우 이점을 얻을 수 있습니다.  사용자 입력 또한 전용 스레드를 사용함으로써 이점을 얻을 수 있습니다.  단일 프로세서 컴퓨터에서, 컴퓨팅 성능이 많이 필요한 작업은 사용자 입력 작업 및 I\/O과 관련된 작업과 함께 진행되지만 컴퓨팅 성능이 많이 필요한 작업끼리는 서로 경쟁을 합니다.  
  
-   간단한 상태 변경에는 `lock` 문\(Visual Basic의 경우 `SyncLock`\)을 사용하지 않고 <xref:System.Threading.Interlocked> 클래스의 메서드를 사용합니다.  `lock` 문은 일반적인 용도의 유용한 도구이지만 원자 단위로 수행되어야 하는 업데이트에는 <xref:System.Threading.Interlocked> 클래스를 사용하는 경우가 성능이 더 좋습니다.  내부적으로는 경합이 없는 경우 단일 잠금 접두사를 실행합니다.  코드 검토에서 다음 예제와 같은 코드를 조사하십시오.  첫 번째 예제에서는 상태 변수 값이 증가합니다.  
  
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
  
     다음과 같이 `lock` 문 대신 <xref:System.Threading.Interlocked.Increment%2A> 메서드를 사용하여 성능을 향상시킬 수 있습니다.  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    >  .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Add%2A> 메서드는 1보다 큰 증분 단위로 원자 단위 업데이트를 제공합니다.  
  
     두 번째 예제에서는 null 참조\(Visual Basic의 경우 `Nothing`\)인 경우에만 참조 형식 변수가 업데이트됩니다.  
  
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
  
     다음과 같이 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드를 대신 사용하면 성능이 향상될 수 있습니다.  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    >  .NET Framework 버전 2.0에서는 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드에 참조 형식을 형식이 안전하게 대체하는 데 사용할 수 있는 제네릭 오버로드가 있습니다.  
  
## 클래스 라이브러리에 대한 권장 사항  
 다중 스레딩을 위한 클래스 라이브러리를 디자인할 때는 다음 지침을 검토하십시오.  
  
-   가능하면 동기화의 필요성을 없애십시오.  많이 사용되는 코드의 경우에는 특히 그렇습니다.  예를 들어, 경합 상태를 없애기 보다는 허용하도록 알고리즘이 조정될 수 있습니다.  불필요한 동기화는 성능을 저하시키고 교착 상태와 경합 상태를 불러올 수 있습니다.  
  
-   정적 데이터\(Visual Basic의 경우 `Shared`\)를 기본적으로 스레드로부터 안전하게 하십시오.  
  
-   인스턴스 데이터는 기본적으로 스레드로부터 안전하게 하지 마십시오.  스레드로부터 안전한 코드를 만들기 위해 잠금을 추가하면 성능이 저하되고, 잠금 경합이 증가하고, 교착 상태가 발생할 수 있습니다.  공용 응용 프로그램 모델에서는 한 번에 한 스레드만 사용자 코드를 실행하므로 스레드 안전에 대한 필요성이 최소화됩니다.  따라서 .NET Framework 클래스 라이브러리는 기본적으로 스레드로부터 안전하지 않습니다.  
  
-   정적 상태를 변경하는 정적 메서드를 제공하지 마십시오.  공용 서버 시나리오에서는 정적 상태가 여러 요청에 공유됩니다. 즉, 여러 스레드가 해당 코드를 동시에 실행할 수 있습니다.  이렇게 되면 스레딩 버그가 발생할 수 있습니다.  데이터를 여러 요청에 공유되지 않는 인스턴스로 캡슐화하는 디자인 패턴을 사용하십시오.  또한 정적 데이터가 동기화되는 경우 상태를 변경하는 정적 메서드 간 호출이 이루어지면 교착 상태나 중복된 동기화가 발생하여 성능이 저하될 수 있습니다.  
  
## 참고 항목  
 [Threading](../../../docs/standard/threading/index.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)