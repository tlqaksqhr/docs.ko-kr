---
title: 기본 속성 액세스가 상속 된 인터페이스 멤버 사이 모호한 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스의 &#39; &lt;interfacename1&gt; &#39; 및 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스의 &#39; &lt;interfacename2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 65a10067284cad3bf56ecdc441ebefa0a740ef53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590857"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a><span data-ttu-id="7933f-102">기본 속성 액세스가 상속 된 인터페이스 멤버 사이 모호한 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스의 &#39; &lt;interfacename1&gt; &#39; 및 &#39; &lt;defaultpropertyname&gt; &#39; 인터페이스의 &#39; &lt;interfacename2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7933f-102">Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39;</span></span>
<span data-ttu-id="7933f-103">인터페이스는 각각 같은 이름의 기본 속성을 선언 하는 두 가지 인터페이스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="7933f-104">컴파일러는 한정 하지 않고이 기본 속성에 대 한 액세스를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="7933f-105">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="7933f-106">지정 하는 경우 `testObj(1)`는 컴파일러의 기본 속성을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="7933f-107">그러나 두 개의 사용 가능한 기본 속성은 상속된 된 인터페이스로 인해 하므로 컴파일러가이 오류를이 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="7933f-108">**오류 ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="7933f-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7933f-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7933f-109">To correct this error</span></span>  
  
-   <span data-ttu-id="7933f-110">동일한 이름 가진 멤버를 상속 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="7933f-111">위 예제의 경우 `testObj` 의 멤버는 필요 하지 않습니다, 예를 들어, `Iface2`, 다음과 같이 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="7933f-112">-또는-</span><span class="sxs-lookup"><span data-stu-id="7933f-112">-or-</span></span>  
  
-   <span data-ttu-id="7933f-113">클래스에서 상속 하는 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="7933f-114">그런 다음 다른 이름의 상속 된 속성의 각 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="7933f-115">그러나 그 중 하나만 구현 하는 클래스의 기본 속성을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="7933f-116">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7933f-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7933f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7933f-117">See Also</span></span>  
 [<span data-ttu-id="7933f-118">인터페이스</span><span class="sxs-lookup"><span data-stu-id="7933f-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
