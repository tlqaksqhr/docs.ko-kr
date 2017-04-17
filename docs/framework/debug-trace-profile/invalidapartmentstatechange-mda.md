---
title: "invalidApartmentStateChange MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid apartment state"
  - "managed debugging assistants (MDAs), invalid apartment state"
  - "InvalidApartmentStateChange MDA"
  - "invalid apartment state changes"
  - "threading [.NET Framework], apartment states"
  - "apartment states"
  - "threading [.NET Framework], managed debugging assistants"
  - "COM apartment states"
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# invalidApartmentStateChange MDA
다음 두 가지 문제 중 하나로 인해 `invalidApartmentStateChange` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
-   COM이 이미 초기화한 스레드의 COM 아파트 상태를 다른 아파트 상태로 변경하려고 시도합니다.  
  
-   스레드의 COM 아파트 상태가 예기치 않게 변경됩니다.  
  
## 증상  
  
-   스레드의 COM 아파트 상태가 요청된 것이 아닙니다.  이로 인해 현재의 스레딩 모델과 다른 스레딩 모델을 가진 COM 구성 요소에 프록시가 사용될 수 있습니다.  그리고 아파트 간 마샬링을 설정하지 않은 인터페이스를 통해 COM 개체를 호출할 경우 <xref:System.InvalidCastException>이 throw될 수 있습니다.  
  
-   해당 스레드의 COM 아파트 상태가 예상과 다릅니다.  이로 인해 RCW\([RCW](../../../docs/framework/interop/runtime-callable-wrapper.md)\)를 호출할 때 <xref:System.InvalidCastException>뿐 아니라 HRESULT가 RPC\_E\_WRONG\_THREAD인 <xref:System.Runtime.InteropServices.COMException>이 발생할 수 있습니다.  또한 일부 단일 스레드 COM 구성 요소를 여러 스레드가 동시에 액세스하여 손상이나 데이터 손실이 초래될 수 있습니다.  
  
## 원인  
  
-   스레드가 이전에 다른 COM 아파트 상태로 초기화되었습니다.  스레드의 아파트 상태는 명시적 또는 암시적으로 설정될 수 있습니다.  명시적 작업에서는 <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName> 속성과 <xref:System.Threading.Thread.SetApartmentState%2A> 및 <xref:System.Threading.Thread.TrySetApartmentState%2A> 메서드를 사용합니다.  <xref:System.Threading.Thread.Start%2A> 메서드를 사용하여 만든 스레드는 스레드 시작 전에 <xref:System.Threading.Thread.SetApartmentState%2A>를 호출하지 않는 한 암시적으로 <xref:System.Threading.ApartmentState>로 설정됩니다.  응용 프로그램의 주 스레드 또한 주 메서드에서 <xref:System.STAThreadAttribute> 특성을 지정하지 않는 한 암시적으로 <xref:System.Threading.ApartmentState>로 초기화됩니다.  
  
-   다른 동시성 모델을 가진 `CoUninitialize` 메서드\(또는 `CoInitializeEx` 메서드\)가 스레드에서 호출됩니다.  
  
## 해결  
 실행하기 전에 스레드의 아파트 상태를 설정하거나 <xref:System.STAThreadAttribute> 특성이나 <xref:System.MTAThreadAttribute> 특성을 응용 프로그램의 주 메서드에 적용합니다.  
  
 두 번째 원인의 경우 스레드가 종료되려 하고 RCW가 없으며 내부 COM 구성 요소를 스레드에서 여전히 사용하고 있을 때까지 호출을 지연하도록 `CoUninitialize` 메서드를 호출하는 코드를 수정하는 것이 좋습니다.  하지만 `CoUninitialize` 메서드를 호출하는 코드를 수정할 수 없는 경우 이 방식으로 초기화되지 않은 스레드에서 RCW를 사용하지 않도록 해야 합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 현재 스레드의 COM 아파트 상태와 코드에서 적용하려 했던 상태입니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 예제에서는 이 MDA를 활성화할 수 있는 상황을 보여 줍니다.  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)