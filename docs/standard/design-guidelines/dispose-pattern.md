---
title: "삭제 패턴 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Dispose 메서드"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] Dispose 메서드"
  - "Finalize 메서드, 클래스 라이브러리 디자인 지침 [.NET Framework]"
  - "Dispose 메서드 이름 사용자 지정"
  - "Finalize 메서드"
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# 삭제 패턴
모든 프로그램 실행을 사용 하는 동안 메모리, 시스템 핸들 또는 데이터베이스 연결과 같은 하나 이상의 시스템 리소스를 획득합니다. 개발자 획득 고 사용한 후 해제 되어야 합니다 때문일 같은 시스템 리소스를 사용할 때는 주의 해야 합니다.  
  
 CLR 자동 메모리 관리에 대 한 지원을 제공합니다. 관리 되는 메모리 \(C\# 연산자를 사용 하 여 할당 된 메모리 `new`\) 명시적으로 해제 하지 않아도 됩니다. 가비지 수집기 \(GC\)에 의해 자동으로 해제 됩니다. 개발자는 메모리를 해제 지루하고 어려운 작업 하 고는.NET Framework에서 제공 하는 전례 없는 생산성에 대 한 주된 이유 중 하나 였습니다.  
  
 그러나 관리 되는 메모리는 많은 시스템 리소스 종류 중 하나일 뿐입니다. 리소스 관리 되는 메모리는 여전히 명시적으로 해제 해야 하 고 관리 되지 않는 리소스 라고 합니다. GC 하지 않으려고 만들어졌습니다 이러한 관리 되지 않는 리소스를 관리 하는 관리 되지 않는 리소스를 관리 하는 것에 대 한 책임을 구성 하는 개발자의 손에 의미입니다.  
  
 CLR 관리 되지 않는 리소스를 해제 합니다. 도움을 제공 합니다.<xref:System.Object?displayProperty=fullName> 가상 메서드를 선언 <xref:System.Object.Finalize%2A> \(종료자 라고도 함\) GC가 호출 되 전에 개체의 메모리는 GC에서 회수 하 고 관리 되지 않는 리소스를 해제 하도록 재정의할 수 있습니다. 종료 가능한 형식으로 종료자를 재정의 하는 형식 참조 됩니다.  
  
 종료자 일부 정리 시나리오에서 효과적 이지만, 두 가지 중요 한 단점이 있습니다.  
  
-   GC 검색 되 면 개체 컬렉션에 적합 한 종료자 호출 됩니다. 이런에서 몇 가지 지정 하지 않은 후 일정 시간 리소스가 더 이상 필요 하지 않습니다. 개발자 정도 리소스 종료자에서 실제로 해제 되는 시점 시간과 리소스를 해제 하려는 경우 사이의 지연 시간 많은 부족 한 리소스 \(리소스를 쉽게 소진 될 수 있습니다\)를 획득 하는 프로그램에서 또는 리소스를 사용 하 여 \(예:: 관리 되지 않는 대용량 메모리 버퍼\)에 유지 하려면 비용이 많이 있는 경우에 허용 되지 않습니다.  
  
-   CLR를 종료자를 호출 해야 하는 경우에 가비지 수집 \(컬렉션 간에 실행 종료자\)의 다음 반올림 될 때까지 해당 개체의 메모리의 컬렉션을 연기 해야 합니다. 이 개체의 메모리 및 모든 개체를 참조 해제 되지 않습니다 오랜 시간에 대 한 것을 의미 합니다.  
  
 따라서 종료자에 전적으로 의존 하기 어려울 수 있기 때문이 부족 한 리소스를 처리할 때 최대한 신속 하 게 관리 되지 않는 리소스를 회수 하는 중요 한 많은 시나리오에서 나 높은 성능이 뛰어난 시나리오의 종료의 오버 헤드가 추가 된 GC는 허용 되지 않습니다.  
  
 프레임 워크는 제공 된 <xref:System.IDisposable?displayProperty=fullName> 개발자는 필요 하지 않은 즉시 관리 되지 않는 리소스를 해제 하는 수동 방법을 제공 하기 위해 구현 해야 하는 인터페이스입니다. 또한 제공 된 <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> 것을 알 수 GC 개체 수동으로 삭제 된 메서드와 필요가 없는 더 이상 종료 되는 경우 개체의 메모리를 회수할 수 이전 합니다. 구현 하는 형식에서 `IDisposable` 인터페이스는 삭제 가능한 형식 이라고 합니다.  
  
 사용 현황 및 종료자의 구현을 표준화 하려는 Dispose 패턴 및 `IDisposable` 인터페이스입니다.  
  
 패턴에 대 한 기본 동기는 구현의 복잡성을 줄일 수는 <xref:System.Object.Finalize%2A> 및 <xref:System.IDisposable.Dispose%2A> 메서드. 복잡 한 메서드 \(차이 장의 뒷부분에 설명 되어\) 전부는 아니지만 일부 코드 경로 공유 한다는 사실에서 기인 합니다. 또한 관리 확정적 리소스에 대 한 언어 지원의 발전 과정에 관련 된 패턴의 일부 요소에 대 한 이유 때문에 있습니다.  
  
 **✓ 수행** 삭제할 수 있는 형식의 인스턴스를 포함 하는 형식에 대해 기본 Dispose 패턴을 구현 합니다. 참조는 [기본 Dispose 패턴](#basic_pattern) 기본적인 패턴에 대 한 자세한 내용은 섹션입니다.  
  
 개발자가 형식을 삭제할 수 있는 다른 개체의 수명을 담당 하면 너무, 삭제 하는 방법입니다. 컨테이너의를 사용 하 여 `Dispose` 메서드는이 가능 하는 편리한 방법입니다.  
  
 **✓ 수행** 기본 Dispose 패턴을 구현 하 고 보유 중인 리소스를 명시적으로 해제 해야 하 고 종료자에 존재 하지 않는 형식에 종료자를 제공 합니다.  
  
 예를 들어, 관리 되지 않는 메모리 버퍼를 저장 하는 형식에 패턴을 구현 되어야 합니다.[종료 가능한 형식](#finalizable_types) 섹션 종료자를 구현 하는 데 관련 된 지침에 설명 합니다.  
  
 **✓ 고려** 클래스에 직접 저장 하지 않으므로 관리 되지 않는 리소스 또는 삭제할 수 있는 개체 이지만 가능성이 수행 하는 하위 유형이 있는 기본 Dispose 패턴을 구현 합니다.  
  
 이러한 좋은 예로 <xref:System.IO.Stream?displayProperty=fullName> 클래스입니다. 모든 리소스를 차지 하지 하는 추상 기본 클래스는 아니지만 대부분의 하위 클래스 및이 때문에이 패턴 구현 합니다.  
  
<a name="basic_pattern"></a>   
## 기본 삭제 패턴  
 패턴의 기본 구현을 구현 하는 것은 `System.IDisposable` 를 선언 하는 인터페이스는 `Dispose(bool)` 간에 공유할 모든 리소스 정리 논리를 구현 하는 메서드는 `Dispose` 메서드와 선택적 종료 자가.  
  
 다음 예제에서는 기본 패턴의 간단한 구현을 보여 줍니다.  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder(){  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        if (disposing){  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 부울 매개 변수 `disposing` 에서 메서드가 호출 되었는지 여부를 나타내는 `IDisposable.Dispose` 구현 또는 종료자에서.`Dispose(bool)` 구현 다른 참조 개체 \(예: 이전 예제의 자원 필드\)에 액세스 하기 전에 매개 변수를 확인 해야 합니다. 이러한 개체에서 메서드를 호출할 때에 액세스 해야는 `IDisposable.Dispose` 구현 \(때는 `disposing` 매개 변수는 true\). 메서드는 종료자에서 호출 하는 경우 \(`disposing` 가 false\)를 다른 개체는 액세스할 수 없습니다. 그 이유는 개체를 순서에 관계 없이 종료 되므로 또는 해당 종속성 중 하나가 될 수 있습니다 이미 종료 되었을 합니다.  
  
 또한이 섹션으로 이미 Dispose 패턴을 구현 하지 않는 기본 클래스에 적용 됩니다. 이미의 패턴을 구현 하는 클래스에서 상속 하는 경우 재정의 하기만 `Dispose(bool)` 메서드를 추가 하는 리소스 정리 논리를 제공 합니다.  
  
 **✓ 수행** 보호 된 가상 void 선언 `Dispose(bool disposing)` 모든 논리를 중앙 집중화 하는 메서드와 관련 관리 되지 않는 리소스를 해제 합니다.  
  
 이 방법에서는 모든 리소스를 정리 발생 해야 합니다. 메서드는 모두 종료자에서 및 `IDisposable.Dispose` 메서드. 매개 변수는 종료 자가 내에서 호출 되는 경우에 false 됩니다. 종료 하는 동안 실행 되는 모든 코드에는 다른 종료 가능한 개체에 액세스 하는 데 사용할 해야 합니다. 종료자를 구현 세부 정보는 다음 섹션에 설명 되어 있습니다.  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ 수행** 구현에서 `IDisposable` 인터페이스를 호출 하 여 `Dispose(true)` 뒤 `GC.SuppressFinalize(this)`합니다.  
  
 에 대 한 호출 `SuppressFinalize` 경우에 발생 해야 `Dispose(true)` 성공적으로 실행 합니다.  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X 하지 않으려면** 매개 변수가 없는 확인 `Dispose` 가상 메서드.  
  
 `Dispose(bool)` 메서드는 서브 클래스에서 재정의 해야 합니다.  
  
```  
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
```  
  
 **X 하지 않으려면** 의 모든 오버 로드 선언는 `Dispose` 이외의 다른 방법 `Dispose()` 및 `Dispose(bool)`합니다.  
  
 `Dispose` 이 패턴을 분류 하 고 구현자, 사용자 및 컴파일러 간에 혼동을 방지 하는 예약 된 단어를 고려 되어야 합니다. 일부 언어 자동으로 특정 형식에이 패턴을 구현 하도록 선택할 수 있습니다.  
  
 **✓ 수행** 허용 된 `Dispose(bool)` 메서드를 두 번 이상 호출할 수 있습니다. 메서드는 첫 번째 호출 후 아무 작업도 수행 하도록 선택할 수 있습니다.  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **X 방지** 내에서 예외를 throw `Dispose(bool)` 포함 하는 프로세스 손상 되어 중요 한 상황에 따라 제외 하 고 \(누수, 일관 되지 않은 공유 상태 등입니다.\).  
  
 사용자가 기대 하는 호출을 `Dispose` 예외가 발생 하지 것입니다.  
  
 경우 `Dispose` 예외를 발생 시킬 수, finally 블록 정리 논리를 더 이상 실행 되지 것입니다. 이 해결 하려면 사용자를 호출할 때마다 래핑할 해야 `Dispose` \(내는 finally 블록\!\) 매우 복잡 한 정리 처리기에 try 블록에서 실행 하는 경우는 `Dispose(bool disposing)` 메서드를 삭제 하는 것이 false 예외가 throw 되지 않습니다. 이렇게 종료자 컨텍스트 내에서 실행 하는 경우 프로세스를 종료 합니다.  
  
 **✓ 수행** throw는 <xref:System.ObjectDisposedException> 개체의 삭제 된 후에 사용할 수 없는 멤버에서입니다.  
  
```  
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething(){  
           if(disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
            ...  
    }  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓ 것이 좋습니다** 메서드를 제공 하 `Close()`, 외에 `Dispose()`, 영역에는 표준 용어 close 인지 합니다.  
  
 이렇게 할 경우 반드시 귀하에 게는 `Close` 구현 동일 `Dispose` 구현는 `IDisposable.Dispose` 메서드 명시적으로 합니다.  
  
```  
public class Stream : IDisposable {  
    IDisposable.Dispose(){  
        Close();  
    }  
    public void Close(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## 종료 가능한 형식  
 종료 가능한 형식은 종료자를 재정의 하 고 종료 코드 경로를 제공 하 여 기본 Dispose 패턴을 확장 하는 형식을 `Dispose(bool)` 메서드.  
  
 종료자는 주로 없기 때문에 시스템의 상태에 대 한 \(일반적으로 유효\) 특정 사항을 가정 프로그램 실행 중에 올바르게 구현 하기가 매우 까다롭습니다. 다음 지침 신중 하 게 고려를 고려해 야 합니다.  
  
 일부 지침에만 적용는 `Finalize` 메서드를 코드에 있지만 종료자에서 호출 합니다. 기본적인 Dispose 패턴 이전에 정의 된 경우 내에서 실행 하는 논리 `Dispose(bool disposing)` 때는 `disposing` 매개 변수는 false입니다.  
  
 기본 클래스 이미 종료 가능한은 기본 Dispose 패턴을 구현 하면 재정의 해서는 안 `Finalize` 다시 합니다. 재정의 해야 하는 대신 바로 `Dispose(bool)` 메서드를 추가 하는 리소스 정리 논리를 제공 합니다.  
  
 다음 코드는 종료 가능한 형식의 예제를 보여 줍니다.  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder(){  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing){  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing){ // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **X 방지** 형식 줄어드는 경우 수행 합니다.  
  
 종료 자가 필요 생각 하는 모든 경우에 주의 합니다. 실제에는 한 성능 및 코드에 해당 하는 복잡성의 관점에서 종료자를 사용 하 여 인스턴스와 관련 된 비용입니다. 와 같은 리소스 래퍼를 사용 하는 것을 선호 <xref:System.Runtime.InteropServices.SafeHandle> 가능한 경우 관리 되지 않는 리소스를 캡슐화 하는 경우 종료 자가 불필요 하 게 만드는 래퍼 자체 리소스 정리를 담당 하기 때문에 있습니다.  
  
 **X 하지 않으려면** 값 형식을 개체로 확인 합니다.  
  
 실제로 참조 형식에만 CLR에 의해 종료 가져오기 및 값 형식에 종료자를 배치 하려고 하므로 무시 됩니다. C\# 및 c \+ \+ 컴파일러에서이 규칙을 적용 합니다.  
  
 **✓ 수행** 형식이 맺지 않은 고유 종료자는 관리 되지 않는 리소스를 해제 해야 하는 경우 종료 가능 형식을 확인 합니다.  
  
 종료자를 구현 하는 경우 호출 합니다 `Dispose(false)` 내에서 모든 리소스 정리 논리를 배치 하 고는 `Dispose(bool disposing)` 메서드.  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        ...  
    }  
}  
```  
  
 **✓ 수행** 종료 가능한 모든 형식에 기본 Dispose 패턴을 구현 합니다.  
  
 이렇게 하면 형식의 사용자를 명시적으로 종료 자가 책임이 같은 리소스의 명확한 정리를 수행 하는 수단입니다.  
  
 **X 하지 않으려면** 는 것은 이미 종료 되었을 위험이 있기 때문에 종료 자가 코드 경로에서 모든 종료 가능한 개체에 액세스 합니다.  
  
 예를 들어 다른 종료 가능한 개체 B에 대 한 참조가 있는 종료 가능 개체는 사용할 수 없습니다 안정적으로 B A의에 종료자 또는 그 반대의 경우도 마찬가지입니다. \(보다 짧은 중요 한 종료에 대 한 약한 정렬 보장\) 임의의 순서로 호출 됩니다.  
  
 또한, 응용 프로그램 도메인 언로드로 동안 또는 프로세스를 종료 하는 동안 정적 변수에 저장 된 개체의 특정 지점에서 수집 얻을 주의 합니다. 종료 가능한 개체 \(또는 정적 변수에 저장 된 값을 사용할 수 있는 정적 메서드를 호출\)를 참조 하는 정적 변수 아닐 액세스 안전 if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=fullName> true를 반환 합니다.  
  
 **✓ 수행** 확인 프로그램 `Finalize` 메서드를 보호 합니다.  
  
 C\#, c \+ \+ 및 VB.NET 개발자 필요가 없습니다이에 대해 걱정할 필요가 컴파일러에서는이 지침을 적용 하는 데 도움이 때문입니다.  
  
 **X 하지 않으려면** 종료자 논리 시스템에 중요 한 오류를 제외 하 고 예외를 할 수 있도록된 이스케이프 합니다.  
  
 CLR \(.NET Framework 버전 2.0\)에서 현재 프로세스 전체를 종료 합니다 종료자에서 예외가 throw 되 면 실행 및 제어 된 방식으로 해제 되는 리소스에서 다른 종료자를 방지 합니다.  
  
 **✓ 것이 좋습니다** 만들고 중요 한 종료 가능한 개체를 사용 하 여 \(포함 된 형식 계층을 사용 하는 형식을 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>\) 스레드 중단을 언로드하고는 종료 자가 반드시 실행 해야 강제 응용 프로그램 도메인 상황이 변하더라도 상황에 대 한 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [일반적인 디자인 패턴](../../../docs/standard/design-guidelines/common-design-patterns.md)   
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)