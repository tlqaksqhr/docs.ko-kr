---
title: "초기화 지연 | Microsoft Docs"
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
  - ".NET의 초기화 지연, 소개"
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# 초기화 지연
개체의 *초기화 지연*은 개체가 처음 사용될 때까지 개체의 생성이 지연됨을 의미합니다. 이 항목에서 *초기화 지연*과 *인스턴스화 지연*은 동의어로 사용됩니다. 초기화 지연은 주로 성능을 개선하고 불필요한 계산을 방지하고 프로그램 메모리 요구 사항을 낮추는 데 사용됩니다.  가장 일반적인 경우는 다음과 같습니다.  
  
-   만들기에 리소스 부담이 큰 개체가 있고, 이 개체가 프로그램에서 사용되지 않을 가능성이 있는 경우.  예를 들어 초기화를 위해 데이터베이스에 연결해야 하는 큰 `Order` 개체 배열이 포함된 `Orders` 속성이 있는 `Customer` 개체가 메모리에 있다고 가정해 보겠습니다.  사용자가 Orders를 표시하라는 요청을 하지 않거나 계산의 데이터를 사용하지 않는 경우 이를 만드는 데 시스템 메모리나 계산 주기를 사용할 이유가 없습니다.  `Lazy<Orders>`를 사용하여 `Orders` 개체를 초기화 지연으로 선언하는 경우 개체가 사용되지 않을 때 시스템 리소스 낭비를 방지할 수 있습니다.  
  
-   만들기에 리소스 부담이 큰 개체가 있고 이 개체의 생성을 리소스 부담이 큰 다른 작업이 완료된 후로 미루려는 경우.  예를 들어 프로그램에서 시작 시 여러 개체 인스턴스를 로드하지만 즉시 필요한 것은 몇 개뿐이라고 가정해 보겠습니다.  필요한 개체가 만들어질 때까지는 필요 없는 개체의 초기화를 미루면 프로그램의 시작 성능을 개선할 수 있습니다.  
  
 직접 코드를 작성하여 초기화 지연을 수행할 수도 있지만 그것보다는 <xref:System.Lazy%601>를 사용하는 것이 좋습니다.  <xref:System.Lazy%601> 및 관련 형식은 스레드 보안도 지원하며 일관적인 예외 전파 정책을 제공합니다.  
  
 다음 표에는 다양한 시나리오에서 초기화 지연을 사용하기 위해 .NET Framework 버전 4가 제공하는 형식 목록이 나와 있습니다.  
  
|형식|설명|  
|--------|--------|  
|<xref:System.Lazy%601>|클래스 라이브러리 또는 사용자 정의 형식을 위한 초기화 지연 의미 체계를 제공하는 래퍼 클래스|  
|<xref:System.Threading.ThreadLocal%601>|스레드 로컬 방식으로 초기화 지연 의미 체계를 제공한다는 점을 제외하면 <xref:System.Lazy%601>와 비슷합니다.  모든 스레드에서 자체의 고유한 값에 액세스할 수 있습니다.|  
|<xref:System.Threading.LazyInitializer>|클래스 오버헤드 없는 개체의 초기화 지연을 위한 고급 `static`\(Visual Basic의 경우 `Shared`\) 메서드를 제공합니다.|  
  
## 기본적인 초기화 지연  
 초기화 지연 형식을 정의하려면\(예: `MyType`\) 다음 예제와 같이 `Lazy<MyType>`\(Visual Basic의 경우 `Lazy(Of MyType)`\)을 사용합니다.  <xref:System.Lazy%601> 생성자에 대리자가 전달되지 않으면 래핑된 형식은 값 속성이 처음 액세스될 때 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>를 사용하여 만들어집니다.  값에 기본 생성자가 없으면 런타임 예외가 throw됩니다.  
  
 다음 예제에서는 `Orders`가 데이터베이스에서 검색한 `Order` 개체 배열을 포함하는 클래스라고 가정합니다.  `Customer` 개체는 `Orders` 인스턴스를 포함하지만 사용자 작업에 따라 `Orders` 개체의 데이터가 필요 없을 수도 있습니다.  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 또한 생성 시 래핑된 형식에 대한 특정 생성자 오버로드를 호출하는 <xref:System.Lazy%601> 생성자의 대리자를 전달하고 다음 예제와 같은 필요한 다른 초기화 단계를 수행할 수 있습니다.  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 Lazy 개체가 만들어진 후 Lazy 변수의 <xref:System.Lazy%601.Value%2A> 속성이 처음 액세스될 때까지 `Orders`의 인스턴스는 만들어지지 않습니다.  처음 액세스될 때 래핑된 형식이 만들어져 반환되며 이후 액세스를 위해 저장됩니다.  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 <xref:System.Lazy%601> 개체는 항상 초기화 시 사용된 같은 개체 또는 값을 반환합니다.  따라서 <xref:System.Lazy%601.Value%2A> 속성은 읽기 전용입니다.  <xref:System.Lazy%601.Value%2A>가 참조 형식을 저장하는 경우 여기에 새 개체를 할당할 수 없습니다. 다만 설정 가능한 public 필드 및 속성의 값은 변경할 수 있습니다. <xref:System.Lazy%601.Value%2A>가 값 형식을 저장하는 경우 값을 수정할 수 없습니다.  그러나 새 인수를 사용하여 변수 생성자를 다시 호출하는 방법으로 새 변수를 만들 수 있습니다.  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 새 지연 인스턴스는 앞의 경우와 마찬가지로 <xref:System.Lazy%601.Value%2A> 속성이 처음 액세스될 때까지 `Orders`를 인스턴스화하지 않습니다.  
  
### 스레드로부터 안전한 초기화  
 기본적으로 <xref:System.Lazy%601> 개체는 스레드로부터 안전합니다.  즉, 생성자가 스레드 보안을 지정하지 않는 경우 생성자가 만드는 <xref:System.Lazy%601> 개체는 스레드로부터 안전합니다.  다중 스레드 시나리오에서 스레드로부터 안전한 <xref:System.Lazy%601> 개체의 <xref:System.Lazy%601.Value%2A> 속성에 액세스하는 첫 스레드는 모든 스레드의 모든 이후 액세스를 위해 이 속성을 초기화하며, 모든 스레드는 이 동일한 데이터를 공유합니다.  따라서 어느 스레드가 개체를 초기화하는지는 중요하지 않으며 경합 상태는 심각하지 않습니다.  
  
> [!NOTE]
>  예외 캐싱을 사용하여 이러한 일관성을 오류 조건으로 확장할 수 있습니다.  자세한 내용은 다음 섹션을 참조 하십시오. [Lazy 개체의 예외](../../../docs/framework/performance/lazy-initialization.md#ExceptionsInLazyObjects).  
  
 다음 예제에서는 동일한 `Lazy<int>` 인스턴스가 세 개의 개별 스레드에 대해 동일한 값을 갖는 것을 보여 줍니다.  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 각 스레드에 대해 별도의 데이터가 필요한 경우 이 항목의 뒷부분에 설명된 대로<xref:System.Threading.ThreadLocal%601> 형식을 사용합니다.  
  
 일부 <xref:System.Lazy%601> 생성자에는 <xref:System.Lazy%601.Value%2A> 속성이 여러 스레드에서 액세스되는지 여부를 지정하는 데 사용되는 `isThreadSafe`라는 부울 매개 변수가 있습니다.  하나의 스레드에서만 이 속성을 액세스하려는 경우에는 `false`를 전달하면 어느 정도의 성능 향상을 얻을 수 있습니다.  여러 스레드에서 이 속성에 액세스하려는 경우에는 `true`를 전달하여 <xref:System.Lazy%601> 인스턴스에서 초기화 시 하나의 스레드에서 예외를 throw하는 경쟁 조건을 올바르게 처리하도록 합니다.  
  
 일부 <xref:System.Lazy%601> 생성자에는 `mode`라는 <xref:System.Threading.LazyThreadSafetyMode> 매개 변수가 있습니다.  이러한 생성자는 추가 스레드 보안 모드를 제공합니다.  다음 표에서는 스레드 보안을 지정하는 생성자 매개 변수가 <xref:System.Lazy%601> 개체의 스레드 보안에 어떠한 영향을 주는지를 보여 줍니다.  각 생성자에는 이러한 매개 변수가 최대 한 개 있습니다.  
  
|개체의 스레드 보안|`LazyThreadSafetyMode` `mode` 매개 변수|부울 `isThreadSafe` 매개 변수|스레드 보안 매개 변수 없음|  
|----------------|-----------------------------------------|-----------------------------|---------------------|  
|완전히 스레드로부터 안전합니다. 한 번에 한 스레드만 값을 초기화하려고 시도합니다.|<xref:System.Threading.LazyThreadSafetyMode>|`true`|예.|  
|스레드로부터 안전하지 않습니다.|<xref:System.Threading.LazyThreadSafetyMode>|`false`|해당 사항 없음.|  
|완전히 스레드로부터 안전합니다. 여러 스레드가 값을 초기화하기 위해 경쟁합니다.|<xref:System.Threading.LazyThreadSafetyMode>|해당 사항 없음.|해당 사항 없음.|  
  
 표에 나와 있듯이 `mode` 매개 변수에 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>을 지정하는 것은 `isThreadSafe` 매개 변수에 `true`를 지정하는 것과 같으며, <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>을 지정하는 것은 `false`를 지정하는 것과 같습니다.  
  
 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>를 지정하면 여러 스레드에서 <xref:System.Lazy%601> 인스턴스의 초기화를 시도할 수 있습니다.  한 스레드만 이 경쟁에서 이길 수 있고 다른 모든 스레드는 성공한 스레드에서 초기화한 값을 받습니다.  초기화하는 동안 스레드에서 예외가 throw되면 해당 스레드는 성공한 스레드에서 설정한 값을 받지 않습니다.  예외가 캐시되지 않으므로 이후에 <xref:System.Lazy%601.Value%2A> 속성에 액세스하려고 시도하는 경우 초기화에 성공할 수 있습니다.  이는 다음 단원에서 설명하는 다른 모드에서 예외가 처리되는 방식과 다릅니다.  자세한 내용은 <xref:System.Threading.LazyThreadSafetyMode> 열거형을 참조하십시오.  
  
<a name="ExceptionsInLazyObjects"></a>   
## Lazy 개체의 예외  
 앞서 언급했듯이 <xref:System.Lazy%601> 개체는 항상 초기화 시 사용된 같은 개체 또는 값을 반환하므로 <xref:System.Lazy%601.Value%2A> 속성은 읽기 전용입니다.  예외 캐싱을 사용하도록 설정한 경우 이 불변성은 예외 동작으로도 확장됩니다.  초기화 지연 개체에 예외 캐싱이 설정되어 있고 <xref:System.Lazy%601.Value%2A> 속성이 처음 액세스될 때 초기화 지연 개체가 초기화 논리에서 예외를 throw하는 경우 이후 <xref:System.Lazy%601.Value%2A> 속성에 대한 모든 액세스 시도에서 동일한 예외가 throw됩니다.  즉, 래핑된 형식의 생성자는 다중 스레드 시나리오에서도 다시 호출되지 않습니다.  따라서 <xref:System.Lazy%601> 개체는 하나의 액세스에서 예외를 throw하고 이후 액세스에서 값을 반환할 수는 없습니다.  
  
 초기화 메서드\(`valueFactory` 매개 변수\)를 사용하는 <xref:System.Lazy%601?displayProperty=fullName> 생성자를 사용할 때는 예외 캐싱이 설정됩니다. 예를 들어 `Lazy(T)(Func(T))` 생성자를 사용할 때 예외 캐싱이 설정됩니다.  생성자가 <xref:System.Threading.LazyThreadSafetyMode> 값\(`mode` 매개 변수\)도 받아 들일 경우 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 또는 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>을 지정합니다.  초기화 메서드를 지정하면 이러한 두 모드에 대해 예외 캐싱이 설정됩니다.  초기화 메서드는 매우 간단할 수 있습니다.  예를 들어 C\#의 경우 `T`: `new Lazy<Contents>(() => new Contents(), mode)` 또는 Visual Basic의 경우 `New Lazy(Of Contents)(Function() New Contents())`에 대해 기본 생성자를 호출할 수 있습니다.  초기화 메서드를 지정하지 않는 <xref:System.Lazy%601?displayProperty=fullName> 생성자를 사용할 경우에는 `T`에 대한 기본 생성자에서 throw되는 예외가 캐시되지 않습니다.  자세한 내용은 <xref:System.Threading.LazyThreadSafetyMode> 열거형을 참조하십시오.  
  
> [!NOTE]
>  `false`로 설정된 `isThreadSafe` 생성자 매개 변수를 사용하거나 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>로 설정된 `mode` 생성자 매개 변수를 사용하여 <xref:System.Lazy%601> 개체를 만들 경우, 단일 스레드로부터 <xref:System.Lazy%601> 개체에 액세스하거나 고유한 동기화를 제공해야 합니다.  이러한 방식은 예외 캐싱을 포함한 개체의 모든 측면에 적용됩니다.  
  
 앞의 단원에서 설명했듯이 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 를 지정하여 만든  <xref:System.Lazy%601>개체는 예외를 다르게 처리합니다.  <xref:System.Threading.LazyThreadSafetyMode>를 사용하면 여러 스레드에서 <xref:System.Lazy%601> 인스턴스를 초기화하기 위해 경쟁할 수 있습니다.  이 경우 예외가 캐시되지 않으므로 <xref:System.Lazy%601.Value%2A> 속성에 액세스하려는 시도는 초기화가 성공할 때까지 계속될 수 있습니다.  
  
 다음 표에서는 <xref:System.Lazy%601> 생성자가 예외 캐싱을 제어하는 방식을 요약해서 보여 줍니다.  
  
|생성자|스레드로부터 안전한 모드|초기화 메서드 사용|예외 캐싱|  
|---------|-------------------|----------------|-----------|  
|Lazy\(T\)\(\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|아니요|아니요|  
|Lazy\(T\)\(Func\(T\)\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|예|예|  
|Lazy\(T\)\(Boolean\)|`True`\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) 또는 `false`\(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|아니요|아니요|  
|Lazy\(T\)\(Func\(T\), Boolean\)|`True`\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) 또는 `false`\(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|예|예|  
|Lazy\(T\)\(LazyThreadSafetyMode\)|사용자 지정|아니요|아니요|  
|Lazy\(T\)\(Func\(T\), LazyThreadSafetyMode\)|사용자 지정|예|사용자가 <xref:> System.Threading.LazyThreadSafetyMode.PublicationOnly?qualifyHint=False&autoUpgrade=True를 지정한 경우 아니요, 그렇지 않으면 예|  
  
## 초기화 지연 속성 구현  
 초기화 지연을 사용하여 public 속성을 구현하려면 속성의 지원 필드를 <xref:System.Lazy%601>로 정의하고 속성의 `get` 접근자에서 <xref:System.Lazy%601.Value%2A> 속성을 반환합니다.  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 <xref:System.Lazy%601.Value%2A> 속성은 읽기 전용이므로 이를 노출하는 속성에는 `set` 접근자가 없습니다.  <xref:System.Lazy%601> 개체가 지원하는 읽기\/쓰기 속성이 필요한 경우 `set` 접근자는 새 <xref:System.Lazy%601> 개체를 만들어 지원 저장소에 할당해야 합니다.  `set` 접근자는 `set` 접근자에 전달된 새 속성 값을 반환하는 람다 식을 만들어 새 <xref:System.Lazy%601> 개체의 생성자에 전달해야 합니다.  <xref:System.Lazy%601.Value%2A> 속성을 다음에 액세스하면 새 <xref:System.Lazy%601>가 초기화되고 <xref:System.Lazy%601.Value%2A> 속성은 자신에 할당된 새 값을 반환합니다.  이러한 복잡한 조정은 <xref:System.Lazy%601>에 기본 제공된 다중 스레드 보호 기능을 보존하기 위한 것입니다.  이렇게 하지 않는 경우 속성 접근자는 <xref:System.Lazy%601.Value%2A> 속성이 반환하는 첫 번째 값을 캐시하고 캐시된 값만 수정해야 하며, 사용자는 이를 수행하기 위해 스레드로부터 안전한 코드를 직접 작성해야 합니다.  <xref:System.Lazy%601> 개체가 지원하는 읽기\/쓰기 속성에 추가 초기화가 필요하기 때문에 성능이 저하될 수도 있습니다.  또한 특정 시나리오에 따라 setter와 getter 간의 경쟁 조건을 방지하기 위해 추가 조정이 필요할 수도 있습니다.  
  
## 스레드 로컬 초기화 지연  
 일부 다중 스레드 시나리오에서 각 스레드에 고유한 전용 데이터를 제공하려는 경우가 있습니다.  이러한 데이터를 *스레드 로컬 데이터*라고 합니다.  .NET Framework 버전 3.5 이상에서는 정적 변수에 `ThreadStatic` 특성을 적용하여 스레드 로컬화할 수 있습니다.  그러나 `ThreadStatic` 특성을 사용할 경우 포착하기 어려운 오류가 발생할 수 있습니다.  예를 들어 다음 예제에서 볼 수 있듯이 기본적인 초기화 문이라도 변수에 액세스하는 첫 스레드에 대해서만 변수가 초기화되는 현상을 일으킬 수 있습니다.  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 다른 모든 스레드에서 변수는 기본값\(0\)을 사용하여 초기화됩니다.  .NET Framework 버전 4에서 대안으로 <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> 형식을 사용하면 사용자가 제공한 <xref:System.Action%601> 대리자에 의해 모든 스레드에서 초기화되는 인스턴스 기반의 스레드 로컬 변수를 만들 수 있습니다.  다음 예제에서 `counter`에 액세스하는 모든 스레드의 시작 값은 1입니다.  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601>은 다음과 같은 기본적인 차이점을 제외하고 <xref:System.Lazy%601>와 거의 같은 방법으로 개체를 래핑합니다.  
  
-   각 스레드는 다른 스레드에서는 액세스할 수 없는 자체의 고유한 전용 데이터를 사용하여 스레드 로컬 변수를 초기화합니다.  
  
-   <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=fullName> 속성은 읽기 전용이며 횟수에 관계없이 수정할 수 있습니다.  이는 예외 전파에 영향을 미칠 수 있습니다. 예를 들어 한 `get` 작업은 예외를 발생시키고 다음 작업은 값을 성공적으로 초기화할 수 있습니다.  
  
-   초기화 대리자가 제공되지 않은 경우 <xref:System.Threading.ThreadLocal%601>은 형식 기본값을 사용하여 래핑된 형식을 초기화합니다.  이런 면에서 <xref:System.Threading.ThreadLocal%601>은 <xref:System.ThreadStaticAttribute> 특성과 일치합니다.  
  
 다음 예제에서는 `ThreadLocal<int>` 인스턴스에 액세스하는 모든 스레드가 각자 고유한 데이터 복사본을 얻는 것을 보여 줍니다.  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## Parallel.For와 ForEach의 스레드 로컬 변수  
 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 메서드 또는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 메서드를 사용하여 병렬로 데이터 소스를 반복하는 경우 스레드 로컬 데이터를 기본적으로 지원하는 오버로드를 사용할 수 있습니다.  이러한 메서드에서 스레드 로컬 특성은 로컬 대리자를 사용하여 데이터를 생성, 액세스 및 정리함으로써 달성됩니다.  자세한 내용은 [How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) 및 [How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md)를 참조하십시오.  
  
## 오버헤드가 낮은 시나리오에서 초기화 지연 사용  
 많은 개체의 초기화를 지연해야 하는 시나리오에서는 <xref:System.Lazy%601>의 각 개체를 래핑하려면 메모리 또는 컴퓨팅 리소스가 너무 많이 소모된다고 판단할 수 있습니다.  또는 초기화 지연이 노출되는 방법에 대한 엄격한 요구 사항이 있을 수 있습니다.  이러한 경우에는 <xref:System.Threading.LazyInitializer?displayProperty=fullName> 클래스의 `static`\(Visual Basic의 경우 `Shared`\) 메서드를 사용하여 <xref:System.Lazy%601> 인스턴스에 래핑하지 않고도 각 개체의 초기화를 지연할 수 있습니다.  
  
 다음 예제에서는 전체 `Orders` 개체를 하나의 <xref:System.Lazy%601> 개체에 래핑하는 대신 필요한 경우에만 개별 `Order` 개체의 초기화를 지연했다고 가정합니다.  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 이 예제에서 모든 루프 반복에 대해 초기화 절차가 호출되었음을 볼 수 있습니다.  다중 스레드 시나리오에서 초기화 절차를 호출하는 첫 번째 스레드는 모든 스레드에 해당 값이 노출되는 스레드입니다.  이후의 스레드에서도 초기화 절차를 호출하지만 그 결과는 사용되지 않습니다.  이러한 종류의 잠재적인 경합 상태를 허용할 수 없는 경우에는 부울 인수와 동기화 개체를 사용하는 <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=fullName>의 오버로드를 사용합니다.  
  
## 참고 항목  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [방법: 개체의 초기화 지연 수행](../../../docs/framework/performance/how-to-perform-lazy-initialization-of-objects.md)