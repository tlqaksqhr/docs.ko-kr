---
title: "Enhancing Debugging with the Debugger Display Attributes | Microsoft Docs"
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
  - "debugger, display attributes"
  - "DebuggerTypeProxyAttribute attribute"
  - "debugging [.NET Framework], debugger display attributes"
  - "DebuggerDisplayAttribute attribute"
  - "display attributes for debugger"
  - "DebuggerBrowsableAttribute attribute"
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Enhancing Debugging with the Debugger Display Attributes
디버거 표시 특성을 사용하면 해당 형식의 런타임 동작을 지정하고 가장 잘 이해하는 형식 개발자가 해당 형식이 디버거에 표시될 때 보이는 모습을 지정할 수도 있습니다.  또한 `Target` 속성을 제공하는 디버거 표시 특성은 소스 코드에 대한 지식이 없는 사용자가 어셈블리 수준에서 적용할 수 있습니다.  <xref:System.Diagnostics.DebuggerDisplayAttribute> 특성은 형식 또는 멤버가 디버거 변수 창에 표시되는 방식을 제어합니다.  <xref:System.Diagnostics.DebuggerBrowsableAttribute> 특성은 필드 또는 속성이 디버거 변수 창에 표시되는 방식을 결정합니다.  <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성은 형식에 대한 프록시 또는 대체 형식을 지정하고 형식이 디버거 창에 표시되는 방식을 변경합니다.  프록시 또는 대체 형식이 있는 변수를 볼 때는 원본 형식 대신 프록시가 디버거 표시 창에 나타납니다. 디버거 변수 창에는 프록시 형식의 공용 멤버만 표시됩니다.  개인 멤버는 표시되지 않습니다.  
  
## DebuggerDisplayAttribute 사용  
 <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> 생성자에는 형식 인스턴스에 대한 값 열에 표시되는 문자열인 단일 인수가 있습니다.  이 문자열에는 중괄호\({ 및 }\)가 들어 있을 수 있습니다.  한 쌍의 중괄호 안에 포함된 텍스트는 식으로 확인됩니다.  예를 들어, 다음 C\# 코드는 더하기 기호\(\+\)를 선택하여 `MyHashtable` 인스턴스에 대해 디버거 표시를 확장할 때 "Count \= 4"를 표시합니다.  
  
```  
[DebuggerDisplay("Count = {count}")]  
class MyHashtable  
{  
    public int count = 4;  
}  
```  
  
 식에서 참조되는 속성에 적용된 특성은 처리되지 않습니다.  C\# 컴파일러의 경우 대상 형식의 현재 인스턴스에 대해 this 참조에 대한 암시적 액세스만 있는 일반 식을 허용합니다.  식은 제한적이며 별칭, 로캘 또는 포인터에는 액세스할 수 없습니다.  C\# 코드에서는 대상 형식의 현재 인스턴스에 대해 `this` 포인터에 암시적으로 액세스할 수 있는 일반 식을 중괄호 사이에 사용할 수 있습니다.  
  
 예를 들어, C\# 개체에 재정의된 `ToString()`이 있는 경우, 디버거에서는 해당 재정의를 호출하고 표준 `{<typeName>}.` 대신 해당 결과를 표시합니다. 따라서 `ToString()`을 재정의한 경우에는 <xref:System.Diagnostics.DebuggerDisplayAttribute>를 사용할 필요가 없습니다.  둘 모두 사용하는 경우에는 <xref:System.Diagnostics.DebuggerDisplayAttribute> 특성이 `ToString()` 재정의보다 우선합니다.  
  
## DebuggerBrowsableAttribute 사용  
 필드나 속성에 <xref:System.Diagnostics.DebuggerBrowsableAttribute>를 적용하여 디버거 창에 필드나 속성을 표시하는 방식을 지정합니다.  이 특성의 생성자는 <xref:System.Diagnostics.DebuggerBrowsableState> 열거형 값 중 하나를 사용하여 다음 상태 중 하나를 지정합니다.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState>는 멤버가 데이터 창에 표시되지 않음을 나타냅니다.  예를 들어, 필드의 <xref:System.Diagnostics.DebuggerBrowsableAttribute>에 이 값을 사용하면 해당 필드가 계층에서 제거되고, 형식 인스턴스의 \+ 기호를 클릭하여 바깥쪽 형식을 확장할 때 해당 필드가 표시되지 않습니다.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState>는 멤버가 기본적으로 표시되기는 하지만 확장되지는 않음을 나타냅니다.  이것은 기본적인 동작입니다.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState>은 멤버 자체는 표시되지 않지만 배열이나 컬렉션인 해당 구성 개체는 표시됨을 나타냅니다.  
  
> [!NOTE]
>  <xref:System.Diagnostics.DebuggerBrowsableAttribute>는 .NET Framework 버전 2.0의 Visual Basic에서 지원되지 않습니다.  
  
 다음 코드 예제에서는 <xref:System.Diagnostics.DebuggerBrowsableAttribute>를 사용하여 이 특성에 따르는 속성이 클래스의 디버그 창에 나타나지 않도록 하는 방법을 보여 줍니다.  
  
```  
[DebuggerBrowsable(DebuggerBrowsableState.Never)]  
public static string y = "Test String";  
```  
  
## DebuggerTypeProxy 사용  
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성은 형식 자체를 변경하는 경우가 아니라 형식의 디버깅 뷰를 근본적으로 크게 변경해야 하는 경우에 사용합니다.  <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성은 개발자가 형식 뷰를 조정할 수 있도록 형식에 대한 표시 프록시를 지정하는 데 사용됩니다.  <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> 속성에 프록시를 사용할 형식이 지정된 경우 <xref:System.Diagnostics.DebuggerDisplayAttribute> 같이 이 특성을 어셈블리 수준에서 사용할 수 있습니다.  이 특성은 특성이 적용된 형식 내에서 발생하는 private 중첩 형식을 지정하는 데 사용하는 것이 좋습니다.  형식 뷰어를 지원하는 식 계산기는 형식이 표시될 때 이 특성을 확인합니다.  특성이 있으면 식 계산기는 특성이 적용된 형식 대신 표시 프록시 형식을 사용합니다.  
  
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>가 있으면 디버거 변수 창에는 프록시 형식의 public 멤버만 표시됩니다.  개인 멤버는 표시되지 않습니다.  데이터 창의 동작은 특성 확장 뷰에 의해 바뀌지 않습니다.  
  
 불필요한 성능 저하 문제를 방지하려면 데이터 창에서 사용자가 형식 옆의 더하기 기호\(\+\)를 클릭하여 개체를 확장하거나 <xref:System.Diagnostics.DebuggerBrowsableAttribute> 특성의 응용 프로그램을 통해 개체를 확장한 경우에만 표시 프록시의 특성을 처리합니다.  즉, 어떤 특성도 표시 형식에 적용하지 않는 것이 좋습니다.  특성은 해당 표시 형식의 본문 내에 적용할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>를 사용하여 디버거 표시 프록시로 사용할 형식을 지정하는 방법을 보여 줍니다.  
  
```  
  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable : Hashtable  
{  
    private const string TestString =   
        "This should not appear in the debug window.";  
  
    internal class HashtableDebugView  
    {  
        private Hashtable hashtable;  
        public const string TestStringProxy =   
            "This should appear in the debug window.";  
  
        // The constructor for the type proxy class must have a   
        // constructor that takes the target type as a parameter.  
        public HashtableDebugView(Hashtable hashtable)  
        {  
            this.hashtable = hashtable;  
        }  
    }  
}  
```  
  
## 예제  
  
### 설명  
 다음 코드 예제는 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에 표시하여 <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute> 및 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성의 적용 결과를 확인할 수 있습니다.  
  
### 코드  
 [!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
 [!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
 [!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]  
  
## 참고 항목  
 <xref:System.Diagnostics.DebuggerDisplayAttribute>   
 <xref:System.Diagnostics.DebuggerBrowsableAttribute>   
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>