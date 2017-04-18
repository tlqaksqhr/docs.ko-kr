---
title: "jitCompilationStart MDA | Microsoft Docs"
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
  - "JIT compilation"
  - "MDAs (managed debugging assistants), JIT compilation"
  - "JitCompilationStart MDA"
  - "managed debugging assistants (MDAs), JIT compilation"
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# jitCompilationStart MDA
JIT\(Just\-In\-Time\) 컴파일러가 함수를 컴파일하기 시작할 때 `jitCompilationStart` MDA\(관리 디버깅 도우미\)가 보고하기 위해 활성화됩니다.  
  
## 증상  
 mscorjit.dll이 프로세스로 로드되기 때문에 기존에 네이티브 이미지 형식인 프로그램의 작업 집합 크기가 늘어납니다.  
  
## 원인  
 프로그램이 종속된 어셈블리 중 일부가 네이티브 형식으로 생성되지 않았거나 생성된 어셈블리가 올바로 등록되지 않았습니다.  
  
## 해결  
 이 MDA를 사용하도록 설정하면 JIT 컴파일되는 함수를 확인할 있습니다.  이 함수를 포함하는 어셈블리가 네이티브 형식으로 생성되고 올바로 등록되었는지 확인합니다.  
  
## 런타임 효과  
 이 MDA는 메서드가 JIT 컴파일되기 직전에 메시지를 기록하므로 이 MDA를 사용하는 경우 성능에 상당한 영향을 미칩니다.  메서드가 인라인인 경우 이 MDA에서는 별도의 메시지를 생성하지 않습니다.  
  
## Output  
 다음 코드 샘플에서는 샘플 출력을 보여 줍니다.  이 샘플 출력에는 어셈블리 테스트에서 클래스 "ns2.CO"의 메서드 "m"이 JIT 컴파일되었다고 표시됩니다.  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## Configuration  
 다음 구성 파일에서는 메서드가 처음으로 JIT 컴파일될 때 보고되는 메서드를 필터링하는 데 사용할 수 있는 다양한 필터를 보여 줍니다.  이름 특성 값을 \*로 설정하여 모든 메서드를 보고하도록 지정할 수 있습니다.  
  
```  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 샘플은 위의 구성 파일과 함께 사용하기 위한 것입니다.  
  
```  
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)