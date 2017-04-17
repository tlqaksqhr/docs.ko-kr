---
title: "이벤트 기반 비동기 패턴 구현 | Microsoft Docs"
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
  - "이벤트 기반 비동기 패턴"
  - "ProgressChangedEventArgs 클래스"
  - "BackgroundWorker 구성 요소"
  - "이벤트 [.NET Framework], 비동기"
  - "비동기 패턴"
  - "AsyncOperationManager 클래스"
  - "스레딩 [.NET Framework], 비동기 기능"
  - "구성 요소 [.NET Framework] 비동기"
  - "AsyncOperation 클래스"
  - "AsyncCompletedEventArgs 클래스"
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 이벤트 기반 비동기 패턴 구현
상당한 지연을 일으킬 수 있는 몇 가지 작업을 사용 하 여 클래스를 작성 하는 경우 비동기 기능을 구현 하 여 주는 것이 좋습니다 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)합니다.  
  
 이벤트 기반 비동기 패턴에는 비동기 기능을 포함 하는 클래스를 패키징하는 표준화 된 방법을 제공 합니다. 도우미 클래스를 사용 하 여 구현 하는 경우 다음과 같은 <xref:System.ComponentModel.AsyncOperationManager>, 프로그램 클래스는 모든 응용 프로그램 모델에서 올바르게 작동 포함 하 여 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 콘솔 응용 프로그램 및 Windows Forms 응용 프로그램입니다.  
  
 이벤트 기반 비동기 패턴을 구현 하는 예제를 보려면 [하는 방법: 이벤트 기반 비동기 패턴을 지 원하는 구성 요소를 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)합니다.  
  
 간단한 비동기 작업에 사용할 수 있습니다는 <xref:System.ComponentModel.BackgroundWorker> 적합 한 구성 요소입니다. 에 대 한 자세한 내용은 <xref:System.ComponentModel.BackgroundWorker>, 참조 [하는 방법: 백그라운드에서 작업 실행](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)합니다.  
  
 다음은이 항목에서 설명 하는 이벤트 기반 비동기 패턴의 기능을 설명 합니다.  
  
-   이벤트 기반 비동기 패턴을 구현 하기 위한 기회  
  
-   비동기 메서드의 이름 지정  
  
-   필요에 따라 취소를 지원 합니다.  
  
-   필요에 따라 IsBusy 속성을 지원 합니다.  
  
-   진행률 보고에 대 한 선택적인 지원  
  
-   필요에 따라 증분 결과 반환 하는 것에 대 한 지원을 제공합니다  
  
-   처리 Out 및 Ref 메서드의 매개 변수  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>이벤트 기반 비동기 패턴을 구현 하기 위한 기회  
 이벤트 기반 비동기 패턴을 구현할 때:  
  
-   클래스의 클라이언트가 필요 하지 않습니다 <xref:System.Threading.WaitHandle> 및 <xref:System.IAsyncResult> 해당 폴링 의미 하는 비동기 작업에 사용할 수 있는 개체 및 <xref:System.Threading.WaitHandle.WaitAll%2A> 또는 <xref:System.Threading.WaitHandle.WaitAny%2A> 클라이언트에서 구축 해야 합니다.  
  
-   원하는 비동기 작업을 익숙한 이벤트/대리자 모델을 사용 하 여 클라이언트에서 관리 하도록 합니다.  
  
 모든 작업은 비동기 구현에 대 한 후보 있지만 긴 대기 시간을 발생 시 키 지 원하는 것 고려해 야 합니다. 특히 해당 하는 작업 클라이언트 메서드를 호출 했는데 추가 개입 없이 완료 되 면 알림이 표시 됩니다. 또한 적절 한는 진행률, 증분 결과 또는 상태 변경의 클라이언트에 게 알리는 주기적으로 계속 해 서 실행 하는 작업입니다.  
  
 이벤트 기반 비동기 패턴을 지원 해야 할 경우 결정에 대 한 자세한 내용은 참조 하십시오. [이벤트 기반 비동기 패턴 구현 시기 결정](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="naming-asynchronous-methods"></a>비동기 메서드의 이름 지정  
 동기 *MethodName* 보려는 비동기 메서드를 제공 합니다.  
  
 정의 *MethodName* `Async` 메서드입니다.  
  
-   `void`를 반환합니다.  
  
-   와 동일한 매개 변수는 *MethodName* 메서드.  
  
-   여러 호출을 허용합니다.  
  
 필요에 따라 정의 *MethodName* `Async` 오버 로드와 동일한 *MethodName*`Async`, 라는 추가 개체 값 매개 변수를 사용 하지만 `userState`합니다. 준비 하는 경우 사용자 메서드의 여러 동시 호출을 관리 하는 경우 이렇게는 `userState` 값은 메서드의 구분 하기 위해 모든 이벤트 처리기에 다시 배달 됩니다. 이 작업을 수행 하기로 나중에 검색에 대 한 사용자 상태를 저장 하는 것입니다.  
  
 별개의 각 *MethodName* `Async` 메서드 서명이 있습니다.  
  
1.  같은 방법으로 클래스에 다음 이벤트를 정의 합니다.  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  다음 대리자를 정의 하 고 <xref:System.ComponentModel.AsyncCompletedEventArgs>합니다. 이 정의 될 수 클래스 자체 외부 있지만 동일한 네임 스페이스에 있습니다.  
  
    ```vb  
    Public Delegate Sub MethodNameCompletedEventHandler( _  
        ByVal sender As Object, _  
        ByVal e As MethodNameCompletedEventArgs)  
  
    Public Class MethodNameCompletedEventArgs  
        Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As MyReturnType  
    End Property  
    ```  
  
    ```csharp  
    public delegate void MethodNameCompletedEventHandler(object sender,   
        MethodNameCompletedEventArgs e);  
  
    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
    {  
        public MyReturnType Result { get; }  
    }  
    ```  
  
    -   확인 된 *MethodName* `CompletedEventArgs` 클래스 필드에 데이터 바인딩이 불가능으로 읽기 전용 속성 및 필드가 아니라 해당 멤버를 노출 합니다.  
  
    -   정의 하지 않으면 <xref:System.ComponentModel.AsyncCompletedEventArgs>-결과 생성 하지 않는 메서드에 대 한 클래스를 파생 합니다. 인스턴스를 사용 하면 <xref:System.ComponentModel.AsyncCompletedEventArgs> 자체입니다.  
  
        > [!NOTE]
        >  실현 가능 하 고 대리자를 다시 사용 하려면 적절 한 때 완벽 하 게 허용 되 고 <xref:System.ComponentModel.AsyncCompletedEventArgs> 형식입니다. 이 경우에 이름이 지정 되지 것입니다 메서드 이름과 동일한 방식으로 지정 된 대리자 및 <xref:System.ComponentModel.AsyncCompletedEventArgs> 는 단일 메서드에 연결 되지 않습니다.  
  
## <a name="optionally-support-cancellation"></a>필요에 따라 취소를 지원 합니다.  
 클래스를 지 원하는 비동기 작업을 취소 하는 경우 아래 설명 된 대로 취소 클라이언트에 노출 되어야 합니다. 취소 지원을 정의 하기 전에 도달 해야 하는 두 가지 결정 사항 되었는지 확인 합니다.  
  
-   앞으로, 추가 될된를 비롯해 클래스 취소를 지 원하는 비동기 작업을 하나씩만 있습니까?  
  
-   여러 보류 중인 작업 취소 지원 기능을 지 원하는 비동기 작업을 수 있습니까? 즉는 *MethodName* `Async` 메서드가 `userState` 매개 변수를 여러 번 호출할 기다리지 않고 끝나기를 허용 않는 것을?  
  
 아래 표에 이러한 두 가지 질문에 대 한 답변을 사용 하 여 취소 메서드에 대 한 서명의 확인 하려면.  
  
### <a name="visual-basic"></a>Visual Basic  
  
||다중 동시 작업 지원|한 번에 하나의 작업|  
|------|------------------------------------------------|----------------------------------|  
|전체 클래스에서 단일 비동기 작업|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|클래스에 여러 비동기 작업|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>C#  
  
||다중 동시 작업 지원|한 번에 하나의 작업|  
|------|------------------------------------------------|----------------------------------|  
|전체 클래스에서 단일 비동기 작업|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|클래스에 여러 비동기 작업|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 정의 하는 경우는 `CancelAsync(object userState)` 메서드, 개체에서 호출 된 간에 구분할 수 있도록 해당 상태 값을 선택할 때 주의 해야 하 고 모든 단일 비동기 메서드 호출 사이의 뿐 아니라 클라이언트 수 있어야 합니다.  
  
 단일 비동기 작업 버전 이름을 지정 하는 결정 *MethodName* `AsyncCancel` Visual Studio의 IntelliSense와 같은 디자인 환경에서 메서드를 보다 쉽게 검색할 수 있는 것에 기반 합니다. 이 관련된 멤버의 그룹화와 비동기 기능와 관련이 없는 다른 멤버 구분 합니다. 있을 수 있다는 추가 하려는 경우 비동기 작업을 추가 이후 버전에서을 정의 하는 것이 좋습니다 `CancelAsync`합니다.  
  
 같은 클래스에는 위의 테이블에서 여러 메서드를 정의 하지 않습니다. 의미가 없어집니다, 또는 메서드의 늘어나서 클래스 인터페이스에 표시 됩니다.  
  
 이러한 방법을 일반적으로 즉시 반환 되며 있고 작업 수도 실제로 취소 되지 않을 수 있습니다. 에 대 한 이벤트 처리기에는 *MethodName* `Completed` 이벤트는 *MethodName* `CompletedEventArgs` 개체에 포함 되어는 `Cancelled` 클라이언트가 취소 발생 여부를 확인 하는 데 사용할 수 있는 필드입니다.  
  
 에 설명 된 취소 의미 체계를 준수할 [이벤트 기반 비동기 패턴을 구현 하기 위한 유용한](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="optionally-support-the-isbusy-property"></a>필요에 따라 IsBusy 속성을 지원 합니다.  
 클래스가 여러 동시 호출을 지원 하지 않으면 공개 해 보십시오는 `IsBusy` 속성입니다. 따라서 개발자가 결정 하 여부는 *MethodName* `Async` 메서드가 예외를 catch 하지 않고 실행 되는 *MethodName* `Async` 메서드.  
  
 준수는 `IsBusy` 의미 체계에 설명 된 [이벤트 기반 비동기 패턴을 구현 하기 위한 유용한](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>진행률 보고에 대 한 선택적인 지원  
 자주 작업 하는 동안 진행률을 보고 하는 비동기 작업에 대 한는 것이 좋습니다. 이벤트 기반 비동기 패턴에서는 이렇게 하는 것에 대 한 지침을 제공 합니다.  
  
-   필요에 따라 비동기 작업에서 발생 되 고 적절 한 스레드에서 호출 이벤트를 정의 합니다. <xref:System.ComponentModel.ProgressChangedEventArgs> 개체는 0에서 100 사이 여야 하는 정수 값 진행률 표시기를 전달 합니다.  
  
-   다음과 같이이 이벤트를 이름을 지정 합니다.  
  
    -   `ProgressChanged`하는 경우 클래스에 비동기 작업이 여러 (또는 이후 버전에서는 여러 비동기 작업을 포함 하도록 확장 될 예정인);  
  
    -   *MethodName* `ProgressChanged` 클래스에 있는 경우 단일 비동기 작업입니다.  
  
     이 이름 지정 선택 방법과 비슷합니다 취소 메서드에 대 한 선택적인 취소 지원 섹션에 설명 된 대로입니다.  
  
 이 이벤트를 사용 해야는 <xref:System.ComponentModel.ProgressChangedEventHandler> 대리자 시그니처 및 <xref:System.ComponentModel.ProgressChangedEventArgs> 클래스입니다. 또는 도메인 관련 진행률 표시기 제공 될 수 있습니다 (인스턴스, 바이트 읽기 및 다운로드 작업에 대 한 총 바이트 수)을 하는 경우를 정의 해야 합니다의 파생된 클래스 <xref:System.ComponentModel.ProgressChangedEventArgs>합니다.  
  
 하나는 `ProgressChanged` 또는 *MethodName* `ProgressChanged` 지 원하는 비동기 메서드의 수에 관계 없이 클래스에 대 한 이벤트입니다. 클라이언트를 사용 해야 하는 `userState` 에 전달 되는 개체는 *MethodName* `Async` 여러 동시 작업에 대 한 진행률 업데이트 내용을 구분 하는 방법입니다.  
  
 여러 작업 진행률을 지원 하 고 각 진행률에 대 한 다른 표시기를 반환 하는 상황이 있을 수 있습니다. 이 경우 단일에서 `ProgressChanged` 이벤트 적절 하 게 되며 여러를 지 원하는 것이 좋습니다 `ProgressChanged` 이벤트입니다. 이 경우 명명 패턴을 사용 하 여 *MethodName* `ProgressChanged` 각 *MethodName* `Async` 메서드.  
  
 설명 하는 진행률 보고 의미를 준수할 [이벤트 기반 비동기 패턴을 구현 하기 위한 유용한](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>필요에 따라 증분 결과 반환 하는 것에 대 한 지원을 제공합니다  
 경우에 따라 비동기 작업이 완료 되기 전에 증분 결과 반환할 수 있습니다. 이 시나리오를 지 원하는 데 사용할 수 있는 옵션의 여러 가지가 있습니다. 다음 몇 가지 예입니다.  
  
### <a name="single-operation-class"></a>단일 작업 클래스  
 클래스는 단일 비동기 작업을 지원 하 고 해당 작업을 다음 증분 결과 반환할 수 있습니다:  
  
-   확장 된 <xref:System.ComponentModel.ProgressChangedEventArgs> 증분 결과 데이터 전송을 위해 입력 하 고 정의 *MethodName* `ProgressChanged` 데이터 확장 된 이벤트입니다.  
  
-   이 발생 *MethodName* `ProgressChanged` 보고할 증분 결과가 없는 경우에 이벤트입니다.  
  
 동일한 이벤트가 발생으로 "모든 작업"에 증분 결과 반환 하는 문제가 있기 때문에 단일 비동기 작업 클래스에만 적용 되는이 솔루션은 *MethodName* `ProgressChanged` 이벤트 않습니다.  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>유형이 같은 증분 결과 사용 하 여 다중 작업 클래스  
 이 경우 클래스에는 각 증분 결과 반환할 수 있는 여러 비동기 메서드를 지원 하 고 모든 이러한 증분 결과는 동일한 형식의 데이터는.  
  
 단일 작업 클래스의 경우 같은 것으로 위에서 설명한 모델에 따라 <xref:System.EventArgs> 구조는 모든 증분 결과에 작동 합니다. 정의 `ProgressChanged` 대신 이벤트는 *MethodName* `ProgressChanged` 이벤트를 다중 비동기 메서드에 적용 됩니다.  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>유형이 다른 증분 결과 사용 하 여 다중 작업 클래스  
 클래스에 여러 비동기 메서드를 지 원하는 경우 각각 다른 유형의 데이터를 반환 해야 합니다.  
  
-   진행률 보고 보고 증분 결과 구분 합니다.  
  
-   별도 정의 *MethodName* `ProgressChanged` 적절 한 지정 된 이벤트 <xref:System.EventArgs> 각 비동기 메서드가 해당 메서드의 증분 결과 데이터를 처리할 수 있습니다.  
  
 에 설명 된 대로 적절 한 스레드에서 해당 이벤트 처리기를 호출 [이벤트 기반 비동기 패턴을 구현 하기 위한 유용한](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>처리 Out 및 Ref 메서드의 매개 변수  
 하지만 사용 `out` 및 `ref` , 일반적으로 사용 하지 않고.NET Framework, 다음은 규칙을 따라야 있을 때:  
  
 동기 메서드 *MethodName*:  
  
-   `out`매개 변수를 *MethodName* 의 되어서는 안 *MethodName*`Async`합니다. 대신, 것의 일부 *MethodName* `CompletedEventArgs` 에서 동일한 매개 변수와 동일한 이름을 가진 *MethodName* (보다 적절 한 이름 제외).  
  
-   `ref`매개 변수를 *MethodName* 의 일부로 표시 되어야 *MethodName*`Async`, 및의 일부로 *MethodName* `CompletedEventArgs` 에서 동일한 매개 변수와 동일한 이름을 가진 *MethodName* (보다 적절 한 이름 제외).  
  
 예를 들어 다음과 같습니다.  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 비동기 메서드 및 해당 <xref:System.ComponentModel.AsyncCompletedEventArgs> 클래스는 다음과 같습니다.  
  
```vb  
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)  
  
Public Class MethodNameCompletedEventArgs  
    Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As Integer   
    End Property  
    Public ReadOnly Property Arg2() As String   
    End Property  
    Public ReadOnly Property Arg3() As String   
    End Property  
End Class  
```  
  
```csharp  
public void MethodNameAsync(string arg1, string arg2);  
  
public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
{  
    public int Result { get; };  
    public string Arg2 { get; };  
    public string Arg3 { get; };  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.ProgressChangedEventArgs>   
 <xref:System.ComponentModel.AsyncCompletedEventArgs>   
 [방법: 이벤트 기반 비동기 패턴을 지 원하는 구성 요소 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [방법: 백그라운드에서 작업 실행](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [방법: 백그라운드 작업을 사용 하는 폼 구현](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [이벤트 기반 비동기 패턴 구현 시기 결정](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)   
 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [이벤트 기반 비동기 패턴을 구현 하기 위한 모범 사례](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)