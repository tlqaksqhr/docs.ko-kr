---
title: gcManagedToUnmanaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9be8165af499729c7b3a95c480cb64d0200e23fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386615"
---
# <a name="gcmanagedtounmanaged-mda"></a>gcManagedToUnmanaged MDA
`gcManagedToUnmanaged` MDA(관리 디버깅 도우미)는 위협이 관리 코드에서 비관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.  
  
## <a name="symptoms"></a>증상  
 COM에 노출된 관리되는 개체를 사용하려고 하면 관리되지 않는 사용자 구성 요소에서 액세스 위반이 발생합니다. COM 개체가 해제된 것처럼 보입니다. 액세스 위반은 비결정적입니다.  
  
## <a name="cause"></a>원인  
 관리되지 않는 구성 요소가 관리되는 COM 개체 계산을 올바르게 참조하지 않을 경우 관리되지 않는 구성 요소가 여전히 개체 참조를 보유하고 있을 때 런타임에서 COM에 노출된 관리되는 개체를 수집할 수 있습니다. 런타임은 가비지 수집 중에 <xref:System.Runtime.InteropServices.Marshal.Release%2A>를 호출하므로 가비지 수집이 발생하기 전에 사용자 구성 요소가 개체를 사용하는 경우 아직 수집되지 않았습니다. 이는 비결정성 소스입니다.  
  
## <a name="resolution"></a>해결  
 이 도우미를 사용하도록 설정하면 개체가 수집에 적격한 시간 사이의 간격이 감소하며, <xref:System.Runtime.InteropServices.Marshal.Release%2A>가 호출되어 수집된 개체에 처음 액세스하려고 시도하는 관리되지 않는 구성 요소를 추적할 수 있도록 도와줍니다.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  
 위협이 관리 코드에서 비관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.  
  
## <a name="output"></a>출력  
 이 MDA는 출력을 생성하지 않습니다.  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)  
 [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
