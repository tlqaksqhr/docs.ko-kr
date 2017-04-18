---
title: "제약이 있는 실행 영역 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CER"
  - "제약이 있는 실행 영역"
ms.assetid: 99354547-39c1-4b0b-8553-938e8f8d1808
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 제약이 있는 실행 영역
CER\(제약이 있는 실행 영역\)는 신뢰할 수 있는 관리 코드를 작성하기 위한 메커니즘의 일부입니다.  CER는 해당 영역의 코드 전체가 실행되는 것을 막는 out\-of\-band 예외가 throw되지 않도록 CLR\(공용 언어 런타임\)을 제한하는 영역을 정의합니다.  이 영역 내에서는 사용자 코드가 out\-of\-band 예외를 throw할 수 있는 코드를 실행할 수 없습니다.  <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 메서드는 `try` 블록 바로 앞에 있어야 하며 `catch`, `finally` 및 `fault` 블록을 제약이 있는 실행 영역으로 표시합니다.  일단 제약이 있는 영역으로 표시되면 코드에서는 강한 안정성 계약을 사용하여 다른 코드를 호출해야 하며, 준비되지 않은 메서드 또는 신뢰할 수 없는 메서드에 대한 가상 호출을 할당하거나 만들려면 실패를 처리할 수 있어야 합니다.  CLR은 CER에서 실행 중인 코드에 대한 스레드 중단을 지연시킵니다.  
  
 제약이 있는 실행 영역은 CLR뿐 아니라 주석이 첨부된 `try` 블록, 특히 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> 클래스에서 파생된 클래스에서 실행되는 결정적 종료자와 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> 메서드를 사용하여 실행되는 코드에서 다양한 형태로 사용됩니다.  
  
## CER 사전 준비  
 CLR은 메모리 부족 현상이 발생하지 않도록 CER를 미리 준비합니다.  JIT\(Just\-In\-Time\) 컴파일이나 형식 로드를 수행하는 동안 CLR에서 메모리가 부족하지 않도록 하려면 사전 준비가 필요합니다.  
  
 개발자는 다음과 같이 코드 영역이 CER임을 나타내야 합니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 특성이 적용된 전체 호출 그래프의 최상위 CER 영역과 메서드가 미리 준비됩니다.  <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>는 <xref:System.Runtime.ConstrainedExecution.Cer> 또는 <xref:System.Runtime.ConstrainedExecution.Cer>의 보장만 나타낼 수 있습니다.  
  
-   가상 디스패치와 같이 정적으로 확인할 수 없는 호출에 대해서는 사전 준비를 수행할 수 없습니다.  이러한 경우에는 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> 메서드를 사용합니다.  <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> 메서드를 사용하는 경우 정리 코드에 <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> 특성을 적용해야 합니다.  
  
## 제약 조건  
 사용자는 CER에서 작성할 수 있는 코드 형식만 사용할 수 있습니다.  이 코드는 다음 작업으로 인해 발생할 수 있는 out\-of\-band 예외를 일으킬 수 없습니다.  
  
-   명시적 할당  
  
-   boxing  
  
-   잠금 가져오기  
  
-   준비되지 않은 메서드를 가상으로 호출  
  
-   약하거나 존재하지 않는 안정성 계약을 사용하여 메서드 호출  
  
 .NET Framework 버전 2.0에서는 이러한 제약 조건이 지침으로 사용되며  진단은 코드 분석 도구를 통해 제공됩니다.  
  
## 안정성 계약  
 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>는 지정된 메서드의 손상 상태와 안정성 보장을 설명하는 사용자 지정 특성입니다.  
  
### 안정성 보장  
 <xref:System.Runtime.ConstrainedExecution.Cer> 열거형 값으로 표시되는 안정성 보장은 다음과 같이 지정된 메서드의 안정성 수준을 나타냅니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  예외 조건에서 메서드가 실패할 수 있습니다.  이 경우 메서드는 성공 또는 실패 여부를 호출 메서드에 다시 보고합니다.  메서드에서 반환 값을 보고할 수 있도록 하려면 CER에 메서드가 포함되어야 합니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  메서드, 형식 또는 어셈블리에 CER 개념이 없으므로 상태 손상에 대한 실질적 완화 없이 CER 내에서 호출할 경우 안전하지 않을 가능성이 높습니다.  CER 보장을 이용하지 않는다는 점에서  이는 다음을 의미합니다.  
  
    1.  예외 조건에서 메서드가 실패할 수 있습니다.  
  
    2.  메서드가 실패 사실을 보고할 수도 있고 보고하지 않을 수도 있습니다.  
  
    3.  메서드가 CER를 사용하도록 작성되지 않습니다\(대부분 이 경우에 해당\).  
  
    4.  명시적으로 메서드, 형식 또는 어셈블리가 성공한 것으로 식별되지 않는 경우 암시적으로 <xref:System.Runtime.ConstrainedExecution.Cer>으로 식별됩니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  예외 조건에서 메서드가 성공합니다.  이러한 수준의 안정성을 얻으려면 CER가 아닌 영역에서 메서드가 호출되어도 CER에서 이 메서드를 포함하도록 구성해야 합니다.  성공 여부에 대한 평가는 주관적이지만 메서드가 의도한 작업을 수행하는 경우 작업에 성공합니다.  예를 들어, Count를 `ReliabilityContractAttribute(Cer.Success)`로 표시하면 이 속성은 CER에서 실행될 때 항상 <xref:System.Collections.ArrayList>에 있는 요소의 개수를 반환하며 내부 필드를 결정되지 않은 상태로 두지 않습니다.  그러나 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드도 성공으로 표시되며, 이는 경합 상태로 인해 해당 값을 새 값으로 대체할 수 없음을 의미합니다.  중요한 점은 메서드가 여기서 설명하는 대로 작동하며, 올바르지만 신뢰할 수 없는 코드가 나타내는 동작보다 특이한 동작에 대해 CER 코드를 작성하지 않아도 된다는 것입니다.  
  
### 손상 수준  
 <xref:System.Runtime.ConstrainedExecution.Consistency> 열거형 값으로 표시되는 손상 수준은 다음과 같이 지정된 환경에서 상태가 손상될 수 있는 정도를 나타냅니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  예외 조건에서 CLR\(공용 언어 런타임\)이 현재 응용 프로그램 도메인의 상태 일관성을 보장하지 않습니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  예외 조건에서 메서드의 상태 손상이 현재 인스턴스로 제한됩니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>. 예외 조건에서 CLR이 상태 일관성을 보장하지 않아 프로세스가 손상될 수 있습니다.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  예외 조건에서 메서드 상태가 손상되지 않습니다.  
  
## 안정성 try\/catch\/finally  
 안정성 `try/catch/finally`는 관리되지 않는 버전과 예측 가능성 보장 수준이 동일한 예외 처리 메커니즘입니다.  `catch/finally` 블록은 CER입니다.  이 블록의 메서드에는 사전 준비가 필요하며 중단할 수 없어야 합니다.  
  
 .NET Framework 버전 2.0에서는 코드가 try 블록 바로 앞에서 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>를 호출하여 해당 try를 신뢰할 수 있음을 런타임에 알립니다.  <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>는 컴파일러 지원 클래스인 <xref:System.Runtime.CompilerServices.RuntimeHelpers>의 멤버입니다.  컴파일러를 통한 가용성을 보류하는 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>를 직접 호출합니다.  
  
## 중단할 수 없는 영역  
 중단할 수 없는 영역은 명령 집합을 CER로 그룹화합니다.  
  
 컴파일러 지원을 통한 가용성을 보류하는 .NET Framework 버전 2.0에서는 사용자 코드에서 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 메서드 호출 다음에 빈 try\/catch 블록을 포함하는 신뢰할 수 있는 try\/catch\/finally를 사용하여 중단할 수 없는 영역을 만듭니다.  
  
## 중요한 종료자 개체  
 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>는 가비지 수집에서 종료자가 실행되도록 합니다.  할당될 때 종료자와 해당 호출 그래프는 미리 준비됩니다.  종료자 메서드는 CER에서 실행되므로 CER와 종료자에 대한 모든 제약 조건을 준수해야 합니다.  
  
 <xref:System.Runtime.InteropServices.SafeHandle> 및 <xref:System.Runtime.InteropServices.CriticalHandle>에서 상속되는 모든 형식은 CER 내에서 해당 종료자가 실행되도록 합니다.  핸들을 해제하는 데 필요한 코드를 실행하려면 <xref:System.Runtime.InteropServices.SafeHandle> 파생 클래스에서 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>을 구현합니다.  
  
## CER에서 허용되지 않는 코드  
 CER에서는 다음 작업이 허용되지 않습니다.  
  
-   명시적 할당  
  
-   잠금 가져오기  
  
-   boxing  
  
-   다차원 배열 액세스  
  
-   리플렉션을 통한 메서드 호출  
  
-   <xref:System.Threading.Monitor.Enter%2A> 또는 <xref:System.IO.FileStream.Lock%2A>  
  
-   보안 검사.  링크 요청만 수행하고 다른 요청은 수행하지 않습니다.  
  
-   COM 개체와 프록시에 대한 <xref:System.Reflection.Emit.OpCodes.Isinst> 및 <xref:System.Reflection.Emit.OpCodes.Castclass>  
  
-   투명 프록시에 대한 필드 가져오기 또는 설정  
  
-   serialization  
  
-   함수 포인터 및 대리자  
  
## 참고 항목  
 [최선의 안정성 구현 방법](../../../docs/framework/performance/reliability-best-practices.md)