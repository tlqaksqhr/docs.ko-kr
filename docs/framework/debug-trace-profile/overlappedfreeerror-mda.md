---
title: "overlappedFreeError MDA | Microsoft Docs"
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
  - "OverlappedFreeError MDA"
  - "overlapped free method call error"
  - "managed debugging assistants (MDAs), overlapped structures"
  - "overlapped structures"
  - "MDAs (managed debugging assistants), overlapped structures"
  - "freeing overlapped structures"
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# overlappedFreeError MDA
`overlappedFreeError` MDA\(관리 디버깅 도우미\)는 겹쳐진 작업를 완료하기 전에 <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=fullName> 메서드를 호출하면 활성화됩니다.  
  
## 증상  
 가비지 수집되는 힙의 액세스 위반 또는 손상입니다.  
  
## 원인  
 작업이 완료되기 전에 겹쳐진 구조가 해제되었습니다.  겹쳐진 포인터를 사용하는 함수는 해제된 후에 구조체에 기록될 수 있습니다.  따라서 다른 개체가 현재 해당 영역을 사용할 수 있기 때문에 힙 손상이 발생할 수 있습니다.  
  
 겹쳐진 작업이 성공적으로 시작하지 않았기 때문에 이 MDA가 오류를 표시하지 않을 수도 있습니다.  
  
## 해결  
 <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> 메서드를 호출하기 전에 겹쳐진 구조체를 사용하여 I\/O 작업을 완료했는지 확인합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 다음은 이 MDA에 대한 샘플 출력입니다.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)