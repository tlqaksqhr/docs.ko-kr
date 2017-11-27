---
title: invalidOverlappedToPinvoke MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1bcfc6411e5f849728f0548b76fa01b3864af640
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="invalidoverlappedtopinvoke-mda"></a>invalidOverlappedToPinvoke MDA
`invalidOverlappedToPinvoke` MDA(관리 디버깅 도우미)는 가비지 수집 힙에서 만들어지지 않은 겹치는 포인터가 특정 Win32 함수에 전달되면 활성화됩니다.  
  
> [!NOTE]
>  기본적으로 P/Invoke 호출이 코드에 정의되어 있고 디버거가 각 메서드의 JustMyCode 상태를 보고하는 경우에만 이 MDA가 활성화됩니다. JustMyCode(예: 확장명이 없는 MDbg.exe)를 인식하지 않는 디버거는 이 MDA를 활성화하지 않습니다. 이러한 디버거는 구성 파일을 사용하고 .mda.config 파일에서 `justMyCode="false"`를 설정하여`(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`) 이 MDA를 사용하도록 설정합니다.  
  
## <a name="symptoms"></a>증상  
 작동 중단 또는 설명할 수 없는 힙 손상이 발생합니다.  
  
## <a name="cause"></a>원인  
 가비지 수집 힙에서 만들어지지 않은 겹치는 포인터가 특정 운영 체제 함수에 전달됩니다.  
  
 다음 표에서는 이 MDA가 추적하는 함수를 보여 줍니다.  
  
|모듈|함수|  
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
|WS2_32.dll|`WSASend`|  
|WS2_32.dll|`WSASendTo`|  
|WS2_32.dll|`WSARecv`|  
|WS2_32.dll|`WSARecvFrom`|  
|MQRT.dll|`MQReceiveMessage`|  
  
 호출을 수행하는 <xref:System.AppDomain>이 언로드될 수 있어 이 조건에서는 힙이 손상될 가능성이 높습니다. <xref:System.AppDomain>이 언로드되면 응용 프로그램 코드는 겹치는 포인터에 대한 메모리를 해제하므로 작업 완료 시 손상이 발생하거나 메모리 누수를 초래하므로 나중에 문제가 발생합니다.  
  
## <a name="resolution"></a>해결  
 <xref:System.Threading.Overlapped.Pack%2A> 메서드를 호출하는 <xref:System.Threading.Overlapped> 개체를 사용하여 함수에 전달될 수 있는 <xref:System.Threading.NativeOverlapped> 구조체를 가져옵니다. <xref:System.AppDomain>이 언로드되면 CLR은 포인터를 해제하기 전에 비동기 작업이 완료될 때까지 기다립니다.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  
 MDA는 CLR에 영향을 미치지 않습니다.  
  
## <a name="output"></a>출력  
 이 MDA의 출력 예제는 다음과 같습니다.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
