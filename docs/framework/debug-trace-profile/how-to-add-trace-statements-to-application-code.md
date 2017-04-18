---
title: "How to: Add Trace Statements to Application Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "tracing [.NET Framework], conditional writes based on switches"
  - "trace statements"
  - "WriteLineIf method"
  - "tracing [.NET Framework], adding trace statements"
  - "Assert method, tracing code"
  - "trace switches, conditional writes based on switches"
  - "WriteIf method"
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Add Trace Statements to Application Code
추적에 가장 자주 사용되는 메서드는 **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, **Fail** 등 수신기로 출력을 작성하는 메서드입니다.  이러한 메서드는 두 범주로 나눌 수 있습니다. 즉, **Write**, **WriteLine** 및 **Fail** 메서드는 모두 무조건 출력을 내보내지만, **WriteIf**, **WriteLineIf** 및 **Assert** 메서드는 부울 조건을 테스트하고 조건의 값에 따라 기록하거나 기록하지 않습니다.  **WriteIf** 및 **WriteLineIf** 메서드는 조건이 `true`인 경우 출력을 내보내며 **Assert** 메서드는 조건이 `false`인 경우 출력을 내보냅니다.  
  
 추적 및 디버깅 전략을 디자인할 때 원하는 출력 모양을 고려해야 합니다.  관련 없는 정보로 채워진 여러 **Write** 문은 읽기 어려운 로그를 생성합니다.  다른 한편으로는 **WriteLine**을 사용하여 별도의 줄에 관련된 문을 넣으면 함께 속한 정보를 구분하기 어렵게 될 수도 있습니다.  일반적으로 여러 소스의 정보를 결합하여 단일 정보 메시지를 생성하려는 경우 여러 **Write** 문을 사용하고, 완전한 단일 메시지를 생성하려는 경우 **WriteLine** 문을 사용합니다.  
  
### 완전한 줄을 작성하려면  
  
1.  <xref:System.Diagnostics.Trace.WriteLine%2A> 또는 <xref:System.Diagnostics.Trace.WriteLineIf%2A> 메서드를 호출합니다.  
  
     이 메서드가 반환하는 메시지의 끝에 캐리지 리턴을 추가합니다. 그러면 **Write**, **WriteIf**, **WriteLine** 또는 **WriteLineIf**에서 반환한 다음 메시지가 다음 줄에서 시작됩니다.  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,   
       "Error in AppendData procedure.");  
  
    ```  
  
### 부분 줄을 작성하려면  
  
1.  <xref:System.Diagnostics.Trace.Write%2A> 또는 <xref:System.Diagnostics.Trace.WriteIf%2A> 메서드를 호출합니다.  
  
     **Write**, **WriteIf**, **WriteLine** 또는 **WriteLineIf**에서 출력하는 다음 메시지는 **Write** 또는 **WriteIf** 문에서 출력하는 메시지와 동일한 줄에서 시작됩니다.  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,   
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
  
    ```  
  
### 메서드를 실행하기 전후에 특정 조건이 있는지 확인하려면  
  
1.  <xref:System.Diagnostics.Trace.Assert%2A> 메서드를 호출합니다.  
  
    ```vb  
    Dim I As Integer = 4  
    Trace.Assert(I = 5, "I is not equal to 5.")  
  
    ```  
  
    ```csharp  
    int I = 4;  
    System.Diagnostics.Trace.Assert(I == 5, "I is not equal to 5.");  
  
    ```  
  
    > [!NOTE]
    >  추적과 디버깅 둘 다에 **Assert**를 사용할 수 있습니다.  이 예제에서는 **수신기** 컬렉션의 수신기로 호출 스택을 출력합니다.  자세한 내용은 [관리 코드의 어설션](../Topic/Assertions%20in%20Managed%20Code.md) 및 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>를 참조하세요.  
  
## 참고 항목  
 <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=fullName>   
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)