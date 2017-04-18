---
title: "invalidCERCall MDA | Microsoft Docs"
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
  - "invalid CER calls"
  - "InvalidCERCall MDA"
  - "MDAs (managed debugging assistants), CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidCERCall MDA
`invalidCERCall` MDA\(관리 디버깅 도우미\)는 CER\(제약이 있는 실행 영역\) 그래프 내에 안정성 계약이 없거나 매우 약한 계약이 있는 메서드에 대한 호출이 있는 경우 활성화됩니다.  약한 계약은 최악의 경우 상태 손상 범위가 호출에 전달되는 인스턴스의 범위보다 크다는 것을 선언하는 계약입니다. 즉, <xref:System.AppDomain> 또는 프로세스 상태가 손상되거나 CER 내에서 호출될 때 해당 결과가 항상 명확하게 계산될 수 없는 계약입니다.  
  
## 증상  
 CER에서 코드를 실행할 때 예기치 않은 결과가 발생합니다.  증상이 명확하지 않습니다.  증상으로는 런타임에서 메서드를 미리 준비하지 못했거나 런타임에 <xref:System.Threading.ThreadAbortException> 예외로부터 메서드를 보호하지 못했기 때문에 호출할 때 신뢰할 수 없는 메서드로의 예상치 못한 <xref:System.OutOfMemoryException>, <xref:System.Threading.ThreadAbortException> 또는 기타 예외가 있을 수 있습니다.  더 중요한 점은 런타임에 메서드에서 발생되는 예외로 인해 <xref:System.AppDomain>이나 프로세스가 CER 목적에 적합하지 않는 불안정한 상태가 된다는 점입니다.  CER를 만드는 이유는 이와 같은 상태의 손상을 피하기 위함입니다.  응용 프로그램 간의 일관성 상태에 대한 정의가 다르므로 손상 상태의 증상은 응용 프로그램에 따라 다릅니다.  
  
## 원인  
 CER 내의 코드는 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>가 없거나 CER의 실행과 호환되지 않는 약한 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>가 있는 함수를 호출합니다.  
  
 안정성 계약 구문과 관련하여 약한 계약은 <xref:System.Runtime.ConstrainedExecution.Consistency> 열거형 값을 지정하지 않거나 <xref:System.Runtime.ConstrainedExecution.Consistency>, <xref:System.Runtime.ConstrainedExecution.Consistency> 또는 <xref:System.Runtime.ConstrainedExecution.Cer>의 <xref:System.Runtime.ConstrainedExecution.Consistency> 값을 지정하는 계약입니다.  이러한 모든 조건은 호출된 코드가 일관된 상태를 유지하기 위하여 CER의 다른 코드의 작업을 방해할 수 있음을 나타냅니다.  CER에서 코드는 매우 명확한 방법으로 오류를 처리할 수 있으므로 응용 프로그램에 중요한 내부 고정식을 유지하고 메모리 부족 예외와 같은 임시 오류의 경우에도 계속해서 실행할 수 있습니다.  
  
 이 MDA의 활성화는 CER에서 호출될 메서드가 호출자가 예상하지 않은 방식 또는 <xref:System.AppDomain>이나 프로세스 상태를 손상되거나 복구할 수 없는 상태로 만드는 방식으로 실패할 가능성이 있음을 나타냅니다.  물론 호출된 코드가 제대로 실행될 수도 있으며 계약이 없다는 점만 문제가 될 수도 있습니다.  그러나 신뢰할 수 있는 코드를 쓰는 것과 관련된 문제는 잠재적이며 계약의 부재는 코드가 제대로 실행되지 못할 가능성을 알려주는 훌륭한 척도입니다.  계약은 프로그래머가 안정적으로 코딩됨을 나타내고 다음에 코드를 수정할 때에도 이러한 보장이 변경되지 않는다는 약속입니다.  즉, 계약은 목적의 선언이며 구현 정보가 아닙니다.  
  
 약한 계약 또는 존재하지 않는 계약이 있는 메서드는 여러 가지 예상치 못한 방법으로 실패할 가능성이 있으므로 런타임에서 지연된 JIT 컴파일, 제네릭 사전 채우기 또는 스레드 중단에 의해 발생되는 메서드로부터 고유의 예상치 못한 실패를 제거하지 않습니다.  즉, 이 MDA가 활성화되면 런타임이 정의할 CER에 호출된 메서드를 포함시키지 않았음을 나타내고, 이 하위 트리를 계속해서 준비하면 오류 가능성을 숨기게 되므로 호출 그래프가 이 노드에서 종료됩니다.  
  
## 해결  
 올바른 신뢰할 수 있는 계약을 함수에 추가하거나 해당 함수 호출의 사용을 피하십시오.  
  
## 런타임 효과  
 CER에서 약한 계약을 호출하면 CER 오류가 발생하여 해당 작업을 완료할 수 없습니다.  이로 인해 <xref:System.AppDomain> 프로세스 상태가 손상될 수 있습니다.  
  
## Output  
 다음은 이 MDA의 출력 샘플입니다.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)