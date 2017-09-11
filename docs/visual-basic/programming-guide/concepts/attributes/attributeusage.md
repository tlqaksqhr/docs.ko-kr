---
title: "AttributeUsage (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c91f2686a03d2590e1aaf166d27c49744bb13c9b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="ef2bd-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef2bd-102">AttributeUsage (Visual Basic)</span></span>
<span data-ttu-id="ef2bd-103">사용자 지정 특성 클래스를 사용할 수 있는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="ef2bd-104">`AttributeUsage`새 특성을 적용 하 하는 방법을 제어 하는 사용자 지정 특성 정의에 적용할 수 있는 특성이입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="ef2bd-105">기본 설정을 명시적으로 적용 하는 경우 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-105">The default settings look like this when applied explicitly:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="ef2bd-106">이 예제에서는 `NewAttribute` 될 수 있는 클래스에 모든 특성 코드 엔터티에 적용 되지만 각 엔터티에 한 번만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="ef2bd-107">기본 클래스에 적용 된 경우 파생된 클래스에서 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="ef2bd-108">`AllowMultiple` 및 `Inherited` 인수는 선택 사항 이므로이 코드는 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="ef2bd-109">첫 번째 `AttributeUsage` 인수 중 하나 이상의 요소가 있어야 합니다.는 <xref:System.AttributeTargets>열거형.</xref:System.AttributeTargets></span><span class="sxs-lookup"><span data-stu-id="ef2bd-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="ef2bd-110">여러 개의 대상 형식은 다음과 같이 OR 연산자와 함께 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 <span data-ttu-id="ef2bd-111">하는 경우는 `AllowMultiple` 인수가로 설정 된 `true`, 다음 다음과 같이 단일 엔터티를 결과 특성을 두 번 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
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
  
 <span data-ttu-id="ef2bd-112">이 경우 `MultiUseAttr` 때문에 반복 해 서 적용할 수 `AllowMultiple` 로 설정 된 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="ef2bd-113">여러 특성을 적용 하기 위해 표시 하는 두 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="ef2bd-114">경우 `Inherited` 로 설정 된 `false`, 다음 특성을 사용 하는 클래스에서 파생 된 클래스에 특성을 상속 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="ef2bd-115">예:</span><span class="sxs-lookup"><span data-stu-id="ef2bd-115">For example:</span></span>  
  
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
  
 <span data-ttu-id="ef2bd-116">이 경우 `Attr1` 에 적용 되지 않으면 `DClass` 상속을 통해.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef2bd-117">주의</span><span class="sxs-lookup"><span data-stu-id="ef2bd-117">Remarks</span></span>  
 <span data-ttu-id="ef2bd-118">`AttributeUsage` 특성은&1; 회용 특성-동일한 클래스에 두 번 이상 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="ef2bd-119">`AttributeUsage`<xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute> 별칭은</span><span class="sxs-lookup"><span data-stu-id="ef2bd-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="ef2bd-120">자세한 내용은 참조 [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef2bd-121">예제</span><span class="sxs-lookup"><span data-stu-id="ef2bd-121">Example</span></span>  
 <span data-ttu-id="ef2bd-122">다음 예제에서는의 효과 보여 줍니다.는 `Inherited` 및 `AllowMultiple` 에 대 한 인수는 `AttributeUsage` 특성과 어떻게 클래스에 적용 되는 사용자 지정 특성을 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef2bd-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
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
  
## <a name="sample-output"></a><span data-ttu-id="ef2bd-123">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="ef2bd-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef2bd-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef2bd-124">See Also</span></span>  
 <span data-ttu-id="ef2bd-125"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="ef2bd-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="ef2bd-126"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="ef2bd-126"><xref:System.Reflection></span></span>   
<span data-ttu-id="ef2bd-127"> [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef2bd-127"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="ef2bd-128"> [특성](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="ef2bd-128"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="ef2bd-129"> [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="ef2bd-129"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="ef2bd-130"> [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ef2bd-130"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="ef2bd-131"> [사용자 지정 특성 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ef2bd-131"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="ef2bd-132"> [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="ef2bd-132"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
