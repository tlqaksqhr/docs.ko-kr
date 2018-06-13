---
title: '방법: 두 개체가 관련이 있는지 확인(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2041f89ffd954e479046eb85c6dd82de1f8793ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649827"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="22908-102">방법: 두 개체가 관련이 있는지 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22908-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="22908-103">생성 된 클래스 간의 관계를 확인 하려면 두 개체를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22908-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="22908-104"><xref:System.Type.IsInstanceOfType%2A> 의 메서드는 <xref:System.Type?displayProperty=nameWithType> 반환 클래스 `True` 지정된 된 클래스는 현재 클래스에서 상속 하는 경우 또는 현재 형식이 지정된 된 클래스에서 지 원하는 인터페이스인 경우.</span><span class="sxs-lookup"><span data-stu-id="22908-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="22908-105">한 개체가 다른 개체의 클래스 또는 인터페이스에서 상속 하는 경우를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="22908-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1.  <span data-ttu-id="22908-106">기본 형식, 호출 수 하 이라고 생각 되는 개체에는 <xref:System.Object.GetType%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="22908-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2.  <span data-ttu-id="22908-107">에 <xref:System.Type?displayProperty=nameWithType> 에서 반환 된 개체 <xref:System.Object.GetType%2A>, 호출 된 <xref:System.Type.IsInstanceOfType%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="22908-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3.  <span data-ttu-id="22908-108">에 대 한 인수 목록에 <xref:System.Type.IsInstanceOfType%2A>, 파생 된 형식의 이라고 생각 되는 개체 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22908-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="22908-109"><xref:System.Type.IsInstanceOfType%2A> 반환 `True` 해당 인수 형식에서 상속 하는 경우는 <xref:System.Type?displayProperty=nameWithType> 개체 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="22908-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22908-110">예제</span><span class="sxs-lookup"><span data-stu-id="22908-110">Example</span></span>  
 <span data-ttu-id="22908-111">다음 예제에서는 한 개체가 다른 개체의 클래스에서 파생 된 클래스를 나타내는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22908-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="22908-112">에 대 한 호출에서 두 개체 변수 위치에 주의 <xref:System.Type.IsInstanceOfType%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="22908-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="22908-113">생성 하는 사람의 기본 형식이 사용 됩니다는 <xref:System.Type?displayProperty=nameWithType> 클래스 및 사람의 파생 된 형식에 대 한 인수로 전달 되는 <xref:System.Type.IsInstanceOfType%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="22908-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22908-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22908-114">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [<span data-ttu-id="22908-115">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="22908-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="22908-116">개체 변수</span><span class="sxs-lookup"><span data-stu-id="22908-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="22908-117">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="22908-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="22908-118">방법: 두 개체가 동일한지 확인</span><span class="sxs-lookup"><span data-stu-id="22908-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
