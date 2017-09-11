---
title: "사용자 지정 특성 (Visual Basic) 만들기 | Microsoft 문서"
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
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
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
ms.openlocfilehash: fbfc3f84f6287d233d475f01869dab63b937a521
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="bd6cb-102">사용자 지정 특성 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="bd6cb-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="bd6cb-103">특성 클래스에서 직접 또는 간접적으로 파생 되는 클래스를 정의 하 여 사용자 지정 특성을 만들 수 있습니다 <xref:System.Attribute>, 식별 하는 쉽고 빠르게 메타 데이터의 특성 정의가 있습니다.</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="bd6cb-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="bd6cb-104">이름으로 형식을 작성 하는 프로그래머의 태그 형식으로 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="bd6cb-105">사용자 지정을 정의할 수 있습니다 `Author` 클래스에 특성:</span><span class="sxs-lookup"><span data-stu-id="bd6cb-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="bd6cb-106">클래스 이름은 특성의 이름이 `Author`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="bd6cb-107">파생 된 `System.Attribute`이므로 사용자 지정 특성 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="bd6cb-108">생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="bd6cb-109">이 예제에서는 `name` 위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="bd6cb-110">모든 공용 읽기 / 쓰기 필드 또는 속성에는 매개 변수 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="bd6cb-111">이 경우 `version` 은 유일한 명명 된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="bd6cb-112">사용 하 여는 `AttributeUsage` 특성 확인을 `Author` 특성 클래스에 대해서만 유효 하 고 `Structure` 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="bd6cb-113">이 새 특성을 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="bd6cb-114">`AttributeUsage`명명 된 매개 변수가 `AllowMultiple`, 있는 하거나 설정할 수 있습니다 사용자 지정 특성 일회용 다용도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="bd6cb-115">다음 코드 예제에서는 다용도 특성이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="bd6cb-116">다음 코드 예제에서는 동일한 형식의 여러 특성 클래스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="bd6cb-117">특성 클래스 속성을 포함 하는 경우 해당 속성에는 읽기 / 쓰기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd6cb-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd6cb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd6cb-118">See Also</span></span>  
 <span data-ttu-id="bd6cb-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="bd6cb-119"><xref:System.Reflection></span></span>   
<span data-ttu-id="bd6cb-120"> [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd6cb-120"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="bd6cb-121"> [사용자 지정 특성 작성](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span><span class="sxs-lookup"><span data-stu-id="bd6cb-121"> [Writing Custom Attributes](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span></span>  
<span data-ttu-id="bd6cb-122"> [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="bd6cb-122"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="bd6cb-123"> [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="bd6cb-123"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="bd6cb-124"> [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span><span class="sxs-lookup"><span data-stu-id="bd6cb-124"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span></span>  
<span data-ttu-id="bd6cb-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span><span class="sxs-lookup"><span data-stu-id="bd6cb-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span></span>
