---
title: "동적으로 형식 로드 및 사용 | Microsoft Docs"
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
  - "형식 동적 로드 및 사용"
  - "초기 바인딩"
  - "암시적 런타임에 바인딩"
  - "런타임에 바인딩, 런타임에 바인딩 정보"
  - "리플렉션, 동적으로 형식 사용"
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 동적으로 형식 로드 및 사용
리플렉션은 [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] 및 JScript 같은 언어 컴파일러에서 암시적으로 런타임에 바인딩을 구현하는 데 사용되는 인프라를 제공합니다.  바인딩은 고유하게 지정된 형식에 해당하는 선언, 즉 구현을 찾는 프로세스입니다.  이 프로세스가 컴파일 타임이 아니라 런타임에 발생하면 런타임에 바인딩이라고 합니다.  [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]에서는 코드에서 암시적으로 런타임에 바인딩을 사용할 수 있으며 Visual Basic 컴파일러는 리플렉션을 사용하여 개체 형식을 가져오는 도우미 메서드를 호출합니다.  이 도우미 메서드에 전달된 인수로 인해 런타임에 적절한 메서드가 호출됩니다.  이러한 인수는 메서드가 호출되는 인스턴스\(개체\), 호출되는 메서드의 이름\(문자열\) 및 호출되는 메서드에 전달할 인수\(개체 배열\)를 나타냅니다.  
  
 다음 예제에서는 Visual Basic 컴파일러가 리플렉션을 사용하여 컴파일 타임에 형식을 알 수 없는 개체에 대해 암시적으로 메서드를 호출합니다.  **HelloWorld** 클래스에는 **PrintHello** 메서드에 전달되는 텍스트와 연결된 "Hello World"를 출력하는 **PrintHello** 메서드가 있습니다.  이 예제에서 호출되는 **PrintHello** 메서드는 실제로 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>이며, Visual Basic 코드에서는 개체\(helloObj\)의 형식이 런타임에 인식\(런타임에 바인딩\)되는 것이 아니라 컴파일 타임에 인식\(초기 바인딩\)되는 것처럼 **PrintHello** 메서드를 호출할 수 있습니다.  
  
```  
Imports System  
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## 사용자 지정 바인딩  
 리플렉션은 컴파일러에서 런타임에 바인딩하기 위해 암시적으로 사용되는 것 이외에, 코드에서 명시적으로 런타임에 바인딩을 수행하기 위해 사용될 수도 있습니다.  
  
 [공용 언어 런타임](../../../docs/standard/clr.md)은 여러 프로그래밍 언어를 지원하며, 이들 언어의 바인딩 규칙은 서로 다릅니다.  초기 바인딩의 경우에는 코드 생성기가 바인딩을 완전히 제어할 수 있습니다.  그러나 리플렉션을 통한 런타임에 바인딩에서는 사용자 지정 바인딩으로 바인딩을 제어해야 합니다.  <xref:System.Reflection.Binder> 클래스를 사용하면 멤버 선택 및 호출을 사용자가 제어할 수 있습니다.  
  
 사용자 지정 바인딩을 사용하여 런타임에 어셈블리를 로드하고, 이 어셈블리에 있는 형식에 대한 정보를 가져오고, 원하는 형식을 지정한 다음, 해당 형식에 대해 메서드를 호출하거나 해당 형식의 필드 또는 속성에 액세스할 수 있습니다.  이 방법은 개체 형식이 사용자 입력에 따라 결정되는 경우처럼 컴파일 타임에 개체의 형식을 알 수 없는 경우에 유용합니다.  
  
 다음 예제에서는 인수 형식을 변환하지 않는 간단한 사용자 지정 바인더를 보여 줍니다.  `Simple_Type.dll`의 코드는 주요 예제 앞에 옵니다.  `Simple_Type.dll`을 빌드한 다음, 프로젝트를 빌드할 때 이에 대한 참조를 프로젝트에 포함시키십시오.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### InvokeMember 및 CreateInstance  
 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>를 사용하여 형식의 멤버를 호출합니다.  [System.Activator](frlrfSystemActivatorClassCreateInstanceTopic) 및 [System.Reflection.Assembly](frlrfSystemReflectionAssemblyClassCreateInstanceTopic) 같은 다양한 클래스의 **CreateInstance** 메서드는 지정된 형식의 새로운 인스턴스를 만드는 **InvokeMember**의 특수 형식입니다.  **Binder** 클래스는 이러한 메서드에서 오버로드 확인과 인수 강제 변환에 사용됩니다.  
  
 다음 예제에서는 인수 강제 변환\(형식 변환\)과 멤버 선택의 세 가지 가능한 조합을 보여 줍니다.  Case 1에서는 인수 강제 변환이나 멤버 선택이 필요하지 않습니다.  Case 2에서는 멤버 선택만 필요합니다.  Case 3에서는 인수 강제 변환만 필요합니다.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 오버로드 확인은 이름이 같은 둘 이상의 멤버를 사용할 수 있을 때 필요합니다.  <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=fullName> 및 <xref:System.Reflection.Binder.BindToField%2A?displayProperty=fullName> 메서드는 단일 멤버에 대한 바인딩을 확인하는 데 사용됩니다.  **Binder.BindToMethod**를 사용할 경우에는 **get** 및 **set** 속성 접근자를 통해 속성도 확인할 수 있습니다.  
  
 **BindToMethod**는 호출할 <xref:System.Reflection.MethodBase>를 반환하거나, 해당 호출이 가능하지 않으면 null 참조\(Visual Basic에서는 **Nothing**\)를 반환합니다.  **MethodBase** 반환 값은 *match* 매개 변수에 포함된 값 중 하나일 필요가 없지만 대개는 이 매개 변수에 포함되는 값 중 하나입니다.  
  
 ByRef 인수가 있을 경우 호출자는 이 인수를 다시 얻으려고 할 수 있습니다.  따라서 **Binder**는 **BindToMethod**가 인수 배열을 조작했을 경우 클라이언트가 인수 배열을 원래 형식으로 다시 매핑할 수 있도록 허용합니다.  이렇게 하려면 호출자는 인수의 순서가 변경되지 않았다는 보장을 받아야 합니다.  인수가 이름으로 전달되면 **Binder**는 인수 배열의 순서를 다시 지정하며 호출자는 이 순서로 인수를 보게 됩니다.  자세한 내용은 <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=fullName>을 참조하십시오.  
  
 사용 가능한 멤버 집합은 형식이나 기본 형식에서 정의된 멤버입니다.  [BindingFlags.NonPublic](frlrfSystemReflectionBindingFlagsClassTopic)이 지정되어 있으면 액세스 가능한 멤버가 이 집합으로 반환됩니다.  **BindingFlags.NonPublic**이 지정되지 않으면 바인더는 액세스 가능성 규칙을 적용해야 합니다.  **Public** 또는 **NonPublic** 바인딩 플래그를 지정하는 경우에는 **Instance** 또는 **Static** 바인딩 플래그도 지정해야 합니다. 그렇지 않으면 멤버가 반환되지 않습니다.  
  
 해당 이름의 멤버가 하나만 있으면 콜백이 필요하지 않으며 해당 메서드에서 바인딩이 수행됩니다.  코드 예제의 Case 1에서는 이 점을 보여 줍니다. 즉, 사용 가능한 **PrintBob** 메서드가 하나만 있으므로 콜백이 필요하지 않습니다.  
  
 사용 가능한 집합에 둘 이상의 멤버가 있으면 모든 메서드가 **BindToMethod**에 전달되며, 그러면 **BindToMethod**가 적절한 메서드를 선택하여 반환합니다.  코드 예제의 Case 2에서는 **PrintValue**라는 메서드가 두 개 있습니다.  이 경우 **BindToMethod**를 호출하면 적절한 메서드가 선택됩니다.  
  
 <xref:System.Reflection.Binder.ChangeType%2A>은 인수 강제 변환\(형식 변환\)을 수행합니다. 인수 강제 변환에서는 실제 인수가 선택된 메서드의 형식 인수의 형식으로 변환됩니다.  **ChangeType**은 형식이 정확히 일치할 경우라도 각 인수에 대해 호출됩니다.  
  
 코드 예제의 Case 3에서는 값이 "5.5"인 **String**  형식의 실제 인수가 **Double** 형식의 형식 인수가 있는 메서드에 전달됩니다.  호출이 성공하려면 문자열 값 "5.5"가 double 값으로 변환되어야 합니다.  **ChangeType**이 이 변환을 수행합니다.  
  
 **ChangeType**은 다음 표에서 볼 수 있는 것처럼 손실이 없는 강제 변환이나 [확장 강제 변환](../../../docs/standard/base-types/type-conversion.md)만 수행합니다.  
  
|소스 형식|대상 형식|  
|-----------|-----------|  
|모든 형식|해당 기본 형식|  
|모든 형식|해당 형식이 구현하는 인터페이스|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|참조가 아닌 형식|참조 형식|  
  
 <xref:System.Type> 클래스에는 **Binder** 형식의 매개 변수를 사용하여 특정 멤버에 대한 참조를 확인하는 **Get** 메서드가 있습니다.  <xref:System.Type.GetConstructor%2A?displayProperty=fullName>, <xref:System.Type.GetMethod%2A?displayProperty=fullName> 및 <xref:System.Type.GetProperty%2A?displayProperty=fullName>는 해당 멤버의 시그니처 정보를 제공하여 현재 형식의 특정 멤버를 검색합니다.  <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=fullName> 및 <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=fullName>는 적절한 메서드의 주어진 시그니처 정보를 선택하기 위해 다시 호출됩니다.  
  
## 참고 항목  
 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 [형식 정보 보기](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [.NET Framework의 형식 변환](../../../docs/standard/base-types/type-conversion.md)