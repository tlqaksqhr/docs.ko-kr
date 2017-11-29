---
title: "디버거 표시 특성을 사용하여 디버깅 향상"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c396a794cd3afa394cbb6b2393257a3103c6239d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a><span data-ttu-id="7aead-102">디버거 표시 특성을 사용하여 디버깅 향상</span><span class="sxs-lookup"><span data-stu-id="7aead-102">Enhancing Debugging with the Debugger Display Attributes</span></span>
<span data-ttu-id="7aead-103">디버거 표시 특성을 통해 해당 형식의 런타임 동작을 지정하고 가장 잘 이해하는 형식의 개발자는 해당 형식이 디버거에 표시될 때 무엇이 표시되는지 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-103">Debugger display attributes allow the developer of the type, who specifies and best understands the runtime behavior of that type, to also specify what that type will look like when it is displayed in a debugger.</span></span> <span data-ttu-id="7aead-104">또한 `Target` 속성을 제공하는 디버거 표시 특성의 경우 소스 코드를 모르는 사용자도 어셈블리 수준에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-104">In addition, debugger display attributes that provide a `Target` property can be applied at the assembly level by users without knowledge of the source code.</span></span> <span data-ttu-id="7aead-105"><xref:System.Diagnostics.DebuggerDisplayAttribute> 특성은 형식 또는 멤버가 디버거 변수 창에 표시되는 방식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-105">The <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute controls how a type or member is displayed in the debugger variable windows.</span></span> <span data-ttu-id="7aead-106"><xref:System.Diagnostics.DebuggerBrowsableAttribute> 특성은 필드 또는 속성이 디버거 변수 창에 표시되는지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-106">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute determines if and how a field or property is displayed in the debugger variable windows.</span></span> <span data-ttu-id="7aead-107"><xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성은 형식에 대한 대체 형식 또는 프록시를 지정하고 디버거 창에 표시되는 방식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-107">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute specifies a substitute type, or a proxy, for a type and changes the way the type is displayed in debugger windows.</span></span> <span data-ttu-id="7aead-108">프록시 또는 대체 형식이 있는 변수를 볼 때 원래 형식 대신 프록시가 디버거 표시 창에 나타납니다**.**</span><span class="sxs-lookup"><span data-stu-id="7aead-108">When you view a variable that has a proxy, or substitute type, the proxy stands in for the original type in the debugger display window**.**</span></span> <span data-ttu-id="7aead-109">디버거 변수 창에는 프록시 형식의 공용 멤버만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-109">The debugger variable windowdisplays only the public members of the proxy type.</span></span> <span data-ttu-id="7aead-110">개인 멤버는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-110">Private members are not displayed.</span></span>  
  
## <a name="using-the-debuggerdisplayattribute"></a><span data-ttu-id="7aead-111">DebuggerDisplayAttribute 사용</span><span class="sxs-lookup"><span data-stu-id="7aead-111">Using the DebuggerDisplayAttribute</span></span>  
 <span data-ttu-id="7aead-112"><xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> 생성자에는 형식 인스턴스에 대한 값 열에 표시되는 문자열인 단일 인수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-112">The <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> constructor has a single argument: a string to be displayed in the value column for instances of the type.</span></span> <span data-ttu-id="7aead-113">이 문자열에는 중괄호({ 및 })가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-113">This string can contain braces ({ and }).</span></span> <span data-ttu-id="7aead-114">중괄호 쌍 안의 텍스트는 식으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-114">The text within a pair of braces is evaluated as an expression.</span></span> <span data-ttu-id="7aead-115">예를 들어 더하기 기호(+)를 선택하여 `MyHashtable` 인스턴스에 대한 디버거 표시를 확장하면 다음 C# 코드로 인해 “Count = 4”가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-115">For example, the following C# code causes "Count = 4" to be displayed when the plus sign (+) is selected to expand the debugger display for an instance of `MyHashtable`.</span></span>  
  
```csharp
[DebuggerDisplay("Count = {count}")]  
class MyHashtable  
{  
    public int count = 4;  
}  
```
  
 <span data-ttu-id="7aead-116">식에서 참조되는 속성에 적용된 특성은 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-116">Attributes applied to properties referenced in the expression are not processed.</span></span> <span data-ttu-id="7aead-117">C# 컴파일러의 경우 대상 형식의 현재 인스턴스에 대한 이 참조에만 암시적으로 액세스할 수 있는 일반 식이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-117">For the C# compiler, a general expression is allowed that has only implicit access to this reference for the current instance of the target type.</span></span> <span data-ttu-id="7aead-118">식은 제한되고 별칭, 로컬 항목 또는 포인터에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-118">The expression is limited; there is no access to aliases, locals, or pointers.</span></span> <span data-ttu-id="7aead-119">C# 코드에서 중괄호 사이에 대상 형식의 현재 인스턴스에 대한 `this` 포인터에만 암시적으로 액세스할 수 있는 일반 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-119">In C# code, you can use a general expression between the braces that has implicit access to the `this` pointer for the current instance of the target type only.</span></span>  
  
 <span data-ttu-id="7aead-120">예를 들어 C# 개체에 재정의된 `ToString()`이 있는 경우 디버거는 이 재정의를 호출하여 표준 `{<typeName>}.` 대신 재정의의 결과를 보여 줍니다. 따라서 `ToString()` 메서드를 재정의한 경우 <xref:System.Diagnostics.DebuggerDisplayAttribute>를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-120">For example, if a C# object has an overridden `ToString()`, the debugger will call the override and show its result instead of the standard `{<typeName>}.` Thus, if you have overridden `ToString()`, you do not need to use <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span></span> <span data-ttu-id="7aead-121">둘 모두 사용하는 경우에는 <xref:System.Diagnostics.DebuggerDisplayAttribute> 특성이 `ToString()` 재정의보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-121">If you use both, the <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute takes precedence over the `ToString()` override.</span></span>  
  
## <a name="using-the-debuggerbrowsableattribute"></a><span data-ttu-id="7aead-122">DebuggerBrowsableAttribute 사용</span><span class="sxs-lookup"><span data-stu-id="7aead-122">Using the DebuggerBrowsableAttribute</span></span>  
 <span data-ttu-id="7aead-123">필드 또는 속성에 <xref:System.Diagnostics.DebuggerBrowsableAttribute>를 적용하여 필드나 속성이 디버거 창에 표시되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-123">Apply the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to a field or property to specify how the field or property is to be displayed in the debugger window.</span></span> <span data-ttu-id="7aead-124">이 특성에 대한 생성자는 다음 상태 중 하나를 지정하는 <xref:System.Diagnostics.DebuggerBrowsableState> 열거형 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-124">The constructor for this attribute takes one of the <xref:System.Diagnostics.DebuggerBrowsableState> enumeration values, which specifies one of the following states:</span></span>  
  
-   <span data-ttu-id="7aead-125"><xref:System.Diagnostics.DebuggerBrowsableState.Never>는 멤버가 데이터 창에 표시되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-125"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indicates that the member is not displayed in the data window.</span></span>  <span data-ttu-id="7aead-126">예를 들어 필드에서 <xref:System.Diagnostics.DebuggerBrowsableAttribute>에 이 값을 사용하면 계층 구조에서 필드가 제거됩니다. 형식 인스턴스에 대한 더하기 기호(+)를 클릭하여 바깥쪽 형식을 확장하면 필드가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-126">For example, using this value for the <xref:System.Diagnostics.DebuggerBrowsableAttribute> on a field removes the field from the hierarchy; the field is not displayed when you expand the enclosing type by clicking the plus sign (+) for the type instance.</span></span>  
  
-   <span data-ttu-id="7aead-127"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed>는 멤버가 표시되지만 기본적으로 확장되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-127"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indicates that the member is displayed but not expanded by default.</span></span>  <span data-ttu-id="7aead-128">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-128">This is the default behavior.</span></span>  
  
-   <span data-ttu-id="7aead-129"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden>은 멤버 자체가 표시되지 않지만 배열이나 컬렉션인 경우 해당 요소 개체가 표시됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-129"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indicates that the member itself is not shown, but its constituent objects are displayed if it is an array or collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aead-130"><xref:System.Diagnostics.DebuggerBrowsableAttribute>는 .NET Framework 버전 2.0의 Visual Basic에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-130">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> is not supported by Visual Basic in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="7aead-131">다음 코드 예제에서는 <xref:System.Diagnostics.DebuggerBrowsableAttribute>를 사용하여 클래스에 대한 디버그 창에서 해당 특성 뒤에 속성이 나타나지 않도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-131">The following code example shows the use of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to prevent the property following it from appearing in the debug window for the class.</span></span>  
  
```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]  
public static string y = "Test String";  
```  
  
## <a name="using-the-debuggertypeproxy"></a><span data-ttu-id="7aead-132">DebuggerTypeProxy 사용</span><span class="sxs-lookup"><span data-stu-id="7aead-132">Using the DebuggerTypeProxy</span></span>  
 <span data-ttu-id="7aead-133">형식의 디버깅 뷰를 완전히 변경하지만 형식 자체는 변경하지 않아야 할 경우 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-133">Use the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute when you need to significantly and fundamentally change the debugging view of a type, but not change the type itself.</span></span> <span data-ttu-id="7aead-134"><xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성은 개발자가 형식에 맞게 뷰를 조정할 수 있도록 형식에 대한 표시 프록시를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-134">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute is used to specify a display proxy for a type, allowing a developer to tailor the view for the type.</span></span>  <span data-ttu-id="7aead-135"><xref:System.Diagnostics.DebuggerDisplayAttribute>처럼 이 특성은 어셈블리 수준에서 사용될 수 있습니다. 이 경우 <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> 속성은 프록시가 사용될 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-135">This attribute, like the <xref:System.Diagnostics.DebuggerDisplayAttribute>, can be used at the assembly level, in which case the <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> property specifies the type for which the proxy will be used.</span></span> <span data-ttu-id="7aead-136">이 특성을 사용하여 특성이 적용되는 형식 내에서 발생하는 전용 중첩 형식을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-136">The recommended usage is that this attribute specifies a private nested type that occurs within the type to which the attribute is applied.</span></span>  <span data-ttu-id="7aead-137">형식 뷰어를 지원하는 식 평가기는 형식이 표시될 때 이 특성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-137">An expression evaluator that supports type viewers checks for this attribute when a type is displayed.</span></span> <span data-ttu-id="7aead-138">특성이 발견된 경우 식 평가기는 특성이 적용되는 형식을 표시 프록시 형식으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-138">If the attribute is found, the expression evaluator substitutes the display proxy type for the type the attribute is applied to.</span></span>  
  
 <span data-ttu-id="7aead-139"><xref:System.Diagnostics.DebuggerTypeProxyAttribute>가 있는 경우 디버거 변수 창에는 프록시 형식의 공용 멤버만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-139">When the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> is present, the debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="7aead-140">개인 멤버는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-140">Private members are not displayed.</span></span> <span data-ttu-id="7aead-141">데이터 창의 동작은 특성이 향상된 뷰를 통해 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-141">The behavior of the data window is not changed by attribute-enhanced views.</span></span>  
  
 <span data-ttu-id="7aead-142">불필요한 성능 저하를 피하기 위해 표시 프록시의 특성은 데이터 창에서 형식 옆의 더하기 기호(+)를 클릭하는 사용자를 통해 또는 <xref:System.Diagnostics.DebuggerBrowsableAttribute> 특성 적용을 통해 개체가 확장될 때까지 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-142">To avoid unnecessary performance penalties, attributes of the display proxy are not processed until the object is expanded, either through the user clicking the plus sign (+) next to the type in a data window, or through the application of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute.</span></span> <span data-ttu-id="7aead-143">따라서 표시 형식에는 특성을 적용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-143">Therefore, it is recommended that no attributes be applied to the display type.</span></span> <span data-ttu-id="7aead-144">특성은 표시 형식 본문 내에서 적용할 수 있고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-144">Attributes can and should be applied within the body of the display type.</span></span>  
  
 <span data-ttu-id="7aead-145">다음 코드 예제에서는 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>를 사용하여 디버거 표시 프록시로 사용할 형식을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-145">The following code example shows the use of the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> to specify a type to be used as a debugger display proxy.</span></span>  
  
```csharp
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
  
## <a name="example"></a><span data-ttu-id="7aead-146">예제</span><span class="sxs-lookup"><span data-stu-id="7aead-146">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7aead-147">설명</span><span class="sxs-lookup"><span data-stu-id="7aead-147">Description</span></span>  
 <span data-ttu-id="7aead-148">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에서 다음 코드 예제를 확인하여 <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute> 및 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 특성을 적용한 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aead-148">The following code example can be viewed in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to see the results of applying the <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>, and <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attributes.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7aead-149">코드</span><span class="sxs-lookup"><span data-stu-id="7aead-149">Code</span></span>  
 [!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
 [!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
 [!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7aead-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aead-150">See Also</span></span>  
 <xref:System.Diagnostics.DebuggerDisplayAttribute>  
 <xref:System.Diagnostics.DebuggerBrowsableAttribute>  
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>
