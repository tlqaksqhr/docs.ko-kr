---
title: AttributeUsage (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aef00d201c3dea82f67395bee0d85f8989afa01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="1a79c-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a79c-102">AttributeUsage (Visual Basic)</span></span>
<span data-ttu-id="1a79c-103">사용자 지정 특성 클래스를 사용하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="1a79c-104">`AttributeUsage`는 새 특성 적용 방법을 제어하기 위해 사용자 지정 특성 정의에 적용할 수 있는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="1a79c-105">기본 설정은 명시적으로 적용될 경우 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-105">The default settings look like this when applied explicitly:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="1a79c-106">이 예제에서 `NewAttribute` 클래스는 모든 특성 가능 코드 엔터티에 적용될 수 있지만 각 엔터티에 한 번만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="1a79c-107">이 특성은 기본 클래스에 적용될 때 파생 클래스가 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="1a79c-108">`AllowMultiple` 및 `Inherited` 인수는 선택 사항이므로 이 코드에 미치는 영향은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="1a79c-109">첫 번째 `AttributeUsage` 인수는 <xref:System.AttributeTargets> 열거형의 요소가 하나 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="1a79c-110">다음과 같이 OR 연산자를 사용하여 여러 대상 형식을 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 <span data-ttu-id="1a79c-111">`AllowMultiple` 인수를 `true`로 설정하면 다음과 같이 결과 특성을 단일 엔터티에 두 번 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 <span data-ttu-id="1a79c-112">이 경우 `AllowMultiple`이 `true`로 설정되므로 `MultiUseAttr`를 반복적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="1a79c-113">여러 특성을 적용하기 위해 표시된 두 형식이 모두 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="1a79c-114">`Inherited`를 `false`로 설정하면 특성이 지정된 클래스에서 파생된 클래스가 특성을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="1a79c-115">예:</span><span class="sxs-lookup"><span data-stu-id="1a79c-115">For example:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 <span data-ttu-id="1a79c-116">이 경우 `Attr1`은 상속을 통해 `DClass`에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a79c-117">주의</span><span class="sxs-lookup"><span data-stu-id="1a79c-117">Remarks</span></span>  
 <span data-ttu-id="1a79c-118">`AttributeUsage` 특성은 단일 사용 특성입니다. 같은 클래스에 두 번 이상 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="1a79c-119">`AttributeUsage`는 <xref:System.AttributeUsageAttribute>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="1a79c-120">자세한 내용은 [리플렉션을 사용하여 특성 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a79c-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a79c-121">예제</span><span class="sxs-lookup"><span data-stu-id="1a79c-121">Example</span></span>  
 <span data-ttu-id="1a79c-122">다음 예제에서는 `AttributeUsage` 특성에 대한 `Inherited` 및 `AllowMultiple`의 영향과 클래스에 적용되는 사용자 지정 특성을 열거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a79c-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a><span data-ttu-id="1a79c-123">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="1a79c-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a79c-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a79c-124">See Also</span></span>  
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [<span data-ttu-id="1a79c-125">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1a79c-125">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="1a79c-126">특성</span><span class="sxs-lookup"><span data-stu-id="1a79c-126">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 [<span data-ttu-id="1a79c-127">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a79c-127">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="1a79c-128">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a79c-128">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="1a79c-129">사용자 지정 특성 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a79c-129">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="1a79c-130">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a79c-130">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
