---
title: "virtualCERCall MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), CER calls"
  - "virtualCERCall MDA"
  - "virtual CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# virtualCERCall MDA
`virtualCERCall` MDA\(관리 디버깅 도우미\)는 CER\(제약이 있는 실행 영역\) 호출 그래프 내의 호출 사이트가 가상 대상, 즉 최종이 아닌 가상 메서드에 대한 가상 호출이나 인터페이스를 사용한 호출을 참조함을 나타내는 경고로 활성화됩니다.  CLR\(공용 언어 런타임\)에서는 중간 언어와 메타데이터 분석만으로 이러한 호출의 대상 메서드를 예측할 수 없습니다.  따라서 호출 트리를 CER 그래프의 일부로 준비할 수 없고 해당 하위 트리의 스레드 중단을 자동으로 차단할 수 없습니다.  이 MDA는 런타임에 호출 대상을 계산하는 데 필요한 추가 정보가 알려진 후 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> 메서드를 명시적으로 호출하여 CER를 확장해야 하는 경우에 대해 경고합니다.  
  
## 증상  
 스레드가 중단되거나 응용 프로그램 도메인이 언로드되면 CER가 실행되지 않습니다.  
  
## 원인  
 CER에는 자동으로 준비할 수 없는 가상 메서드에 대한 호출이 포함됩니다.  
  
## 해결  
 가상 메서드에 대해 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>를 호출합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
  
```  
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
  
```  
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of   
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)