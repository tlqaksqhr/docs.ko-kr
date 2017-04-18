---
title: "invalidOverlappedToPinvoke MDA | Microsoft Docs"
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
  - "overlapped pointers"
  - "managed debugging assistants (MDAs), overlapped pointers"
  - "invalid overlapped pointer to platform invoke"
  - "InvalidOverlappedToPinvoke MDA"
  - "MDAs (managed debugging assistants), overlapped pointers"
  - "pointers, overlapped"
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidOverlappedToPinvoke MDA
`invalidOverlappedToPinvoke` MDA\(관리 디버깅 도우미\)는 가비지 수집 힙에서 만들어지지 않은 중첩 포인터가 특정 Win32 함수에 전달될 때 활성화됩니다.  
  
> [!NOTE]
>  기본적으로, P\/Invoke 호출이 코드에 정의되어 있고 디버거가 각 메서드의 JustMyCode 상태를 전하는 경우에만 이 MDA가 활성화됩니다.  확장자가 없는 MDbg.exe와 같은 JustMyCode를 이해하지 못하는 디버거는 이 MDA를 활성화하지 못합니다.  구성 파일을 사용하고 .mda.config 파일에서 명시적으로 `justMyCode="false"`를 설정하여`(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`\) 이 MDA를 이러한 디버거에 대해 활성화할 수 있습니다.  
  
## 증상  
 충돌 또는 설명할 수 없는 힙 손상이 발생합니다.  
  
## 원인  
 가비지 수집 힙에서 만들어지지 않은 중첩 포인터는 특정 운영 체제 함수에 전달됩니다.  
  
 다음 표에서는 이 MDA가 추적하는 함수를 보여 줍니다.  
  
|Module|Function|  
|------------|--------------|  
|HttpApi.dll|`HttpReceiveHttpRequest`|  
|IpHlpApi.dll|`NotifyAddrChange`|  
|kernel32.dll|`ReadFile`|  
|kernel32.dll|`ReadFileEx`|  
|kernel32.dll|`WriteFile`|  
|kernel32.dll|`WriteFileEx`|  
|kernel32.dll|`ReadDirectoryChangesW`|  
|kernel32.dll|`PostQueuedCompletionStatus`|  
|MSWSock.dll|`ConnectEx`|  
|WS2\_32.dll|`WSASend`|  
|WS2\_32.dll|`WSASendTo`|  
|WS2\_32.dll|`WSARecv`|  
|WS2\_32.dll|`WSARecvFrom`|  
|MQRT.dll|`MQReceiveMessage`|  
  
 호출을 생성하는 <xref:System.AppDomain>이 언로드될 수 있으므로 이 상황에서는 힙 손상의 가능성이 높습니다.  <xref:System.AppDomain>이 언로드되면 응용 프로그램 코드에서 중첩 포인터에 대한 메모리를 해제하여 작업이 완료될 때 손상을 발생시키거나 해당 코드에서 메모리를 누수하여 나중에 장애가 발생합니다.  
  
## 해결  
 함수에 전달할 수 있는 <xref:System.Threading.NativeOverlapped> 구조를 가져오려면 <xref:System.Threading.Overlapped.Pack%2A> 메서드를 호출하는 <xref:System.Threading.Overlapped> 개체를 사용합니다.  <xref:System.AppDomain>이 언로드되면 CLR은 포인터를 해제하기 전에 비동기 작업이 완료될 때까지 기다립니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 다음은 이 MDA의 출력 예제입니다.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)