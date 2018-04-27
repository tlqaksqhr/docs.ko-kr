---
title: contextSwitchDeadlock MDA
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: 22
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f3ee9aef3bc824ee25e577a5dbd14aeaa210be3
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="contextswitchdeadlock-mda"></a>contextSwitchDeadlock MDA
`contextSwitchDeadlock` MDA(관리 디버깅 도우미)는 COM 컨텍스트 전환이 시도되는 동안 교착 상태가 감지되면 활성화됩니다.  
  
## <a name="symptoms"></a>증상  
 가장 일반적인 증상은 관리 코드에서 관리되지 않는 COM 구성 요소에 대한 호출이 반환되지 않는 것입니다.  다른 증상은 시간이 지남에 따라 메모리 사용이 늘어나는 것입니다.  
  
## <a name="cause"></a>원인  
 가장 가능성 있는 원인은 STA(단일 스레드 아파트) 스레드가 메시지를 펌핑하지 않는 것입니다. STA 스레드가 메시지를 펌핑하지 않고 기다리고 있거나, 시간이 많이 걸리는 작업을 수행 중이며 메시지 큐가 펌핑되는 것을 허용하지 않고 있습니다.  
  
 시간이 지남에 따라 메모리 사용이 늘어나는 것은 종료자 스레드가 관리되지 않는 COM 구성 요소에 대해 `Release`를 호출하려고 하고 구성 요소가 반환되지 않기 때문입니다.  따라서 종료자가 다른 개체를 회수하지 못합니다.  
  
 기본적으로 Visual Basic 콘솔 응용 프로그램의 주 스레드에 대한 스레딩 모델은 STA입니다. 이 MDA는 STA 스레드가 직접적으로 또는 공용 언어 런타임이나 타사 컨트롤을 통해 간접적으로 COM 상호 운용성을 사용하는 경우 활성화됩니다.  Visual Basic 콘솔 응용 프로그램에서 이 MDA가 활성화되지 않도록 하려면 Main 메서드에 <xref:System.MTAThreadAttribute> 특성을 적용하거나 메시지를 펌핑하도록 응용 프로그램을 수정합니다.  
  
 다음 조건이 모두 충족되면 이 MDA가 잘못 활성화될 수 있습니다.  
  
-   응용 프로그램이 직접적으로 또는 라이브러리를 통해 간접적으로 STA 스레드에서 COM 구성 요소를 만듭니다.  
  
-   응용 프로그램이 디버거에서 중지되었고 사용자가 응용 프로그램을 계속했거나 단계 작업을 수행했습니다.  
  
-   관리되지 않는 디버깅이 사용하도록 설정되지 않았습니다.  
  
 MDA가 잘못 활성화되었는지 확인하려면 모든 중단점을 사용하지 않도록 설정하고 응용 프로그램을 다시 시작한 후 응용 프로그램이 중지되지 않고 실행되도록 허용합니다. MDA가 활성화되지 않으면 초기 활성화가 잘못된 것입니다. 이 경우 MDA를 사용하지 않도록 설정하여 디버깅 세션의 방해를 방지합니다.  
  
> [!NOTE]
>  이 MDA는 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 이상 버전의 기본 집합에 있습니다. Visual Studio에서 호스팅 프로세스 사용은 기본 집합에 있는 Mda를 비활성화할 수 없습니다. 호스팅 프로세스는 기본적으로 사용하도록 설정되므로 명시적으로 사용하지 않도록 설정되어야 합니다. MDA를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)의 “MDA 사용 및 사용 안 함”을 참조하세요.  
  
## <a name="resolution"></a>해결  
 STA 메시지 펌핑 관련 COM 규칙을 따릅니다.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  
 이 MDA는 CLR에 아무런 영향을 미치지 않으며, COM 컨텍스트에 대한 데이터를 보고할 뿐입니다.  
  
## <a name="output"></a>출력  
 현재 컨텍스트 및 대상 컨텍스트를 설명하는 메시지입니다.  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
