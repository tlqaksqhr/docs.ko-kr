---
title: "openGenericCERCall MDA | Microsoft Docs"
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
  - "open generic CER calls"
  - "constrained execution regions"
  - "openGenericCERCall MDA"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
  - "generics [.NET Framework], open generic CER calls"
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# openGenericCERCall MDA
루트 메서드에서 제네릭 형식 변수를 가진 CER\(제약이 있는 실행 영역\) 그래프가 JIT 컴파일 또는 네이티브 이미지 생성 시간에 처리되는 중이며, 하나 이상의 제네릭 형식 변수가 개체 참조 형식임을 경고하기 위해 `openGenericCERCall` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
## 증상  
 스레드가 중단되거나 응용 프로그램 도메인이 언로드될 때 CER 코드가 실행되지 않습니다.  
  
## 원인  
 JIT 컴파일 시간에 개체 참조 형식이 들어 있는 인스턴스는 결과 코드가 공유되므로 하나의 표현일 뿐이며 각 개체 참조 형식 변수는 임의의 모든 개체 참조 형식이 될 수 있습니다.  이렇게 하면 일부 런타임 리소스의 준비를 미리 하지 않아도 됩니다.  
  
 특히 제네릭 형식 변수가 있는 메서드는 백그라운드에서 리소스를 나중에 할당할 수 있습니다.  이러한 메서드를 제네릭 사전 항목이라고 합니다.  예를 들어 `List<T> list = new List<T>();` 문\(여기서 `T`는 제네릭 형식 변수임\)의 경우 런타임은 정확한 인스턴스\(예: `List<Object>, List<String>` `` 등\)를 조회하고 만들어야 합니다.  이 작업은 메모리 부족과 같은 개발자가 제어할 수 없는 다양한 이유로 인해 실패할 수 있습니다.  
  
 이 MDA는 정확한 인스턴스가 있는 경우가 아닌 JIT 컴파일 시간에만 활성화되어야 합니다.  
  
 이 MDA가 활성화되면 잘못된 인스턴스에 대해 CER가 작동하지 않는 증상이 나타날 수 있습니다.  사실상 런타임은 MDA가 활성화되는 환경에서 CER를 구현하지 않습니다.  따라서 개발자가 CER의 공유 인스턴스를 사용하는 경우 사용되는 CER 영역 내에서 JIT 컴파일 오류, 제네릭 형식 로딩 오류 또는 스레드 중단은 확인되지 않습니다.  
  
## 해결  
 CER가 포함되어 있을 수 있는 메서드에 개체 참조 형식으로 된 제네릭 형식 변수는 사용하지 마십시오.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 다음은 이 MDA의 출력 샘플입니다.  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 CER 코드가 실행되지 않습니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Runtime.CompilerServices;  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        CallGenericMethods();  
    }  
    static void CallGenericMethods()  
    {  
        // This call is correct. The instantiation of the method  
        // contains only nonreference types.  
        MyClass.GenericMethodWithCer<int>();  
  
        // This call is incorrect. A shared version of the method that  
        // cannot be completely analyzed will be JIT-compiled. The   
        // MDA will be activated at JIT-compile time, not at run time.  
        MyClass.GenericMethodWithCer<String>();  
    }  
}  
  
    class MyClass  
{  
    public static void GenericMethodWithCer<T>()  
    {  
        RuntimeHelpers.PrepareConstrainedRegions();  
        try  
        {  
  
        }  
        finally  
        {  
            // This is the start of the CER.  
            Console.WriteLine("In finally block.");  
        }  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)