---
title: 참조할 수 없습니다. &#39; &lt;이름&gt; &#39; 값 형식 필드의 멤버 이기 때문에 &#39; &lt;이름&gt; &#39; 클래스의 &#39; &lt;classname&gt; &#39;가 &#39;System.MarshalByRefObject&#39; 기본 클래스
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: f44d33c9d51148e6bbcfbf5db4dbc115101df1f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586349"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="a82f4-102">참조할 수 없습니다. &#39; &lt;이름&gt; &#39; 값 형식 필드의 멤버 이기 때문에 &#39; &lt;이름&gt; &#39; 클래스의 &#39; &lt;classname&gt; &#39;가 &#39;System.MarshalByRefObject&#39; 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="a82f4-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="a82f4-103">`System.MarshalByRefObject` 클래스를 사용 하면 응용 프로그램 도메인 경계를 넘어 개체에 대 한 원격 액세스를 지 원하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a82f4-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="a82f4-104">형식에서 상속 해야 합니다는 `MarshalByRejectObject` 클래스 응용 프로그램 도메인 경계는 형식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a82f4-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="a82f4-105">개체의 멤버는 만든 응용 프로그램 도메인 외부에서 사용할 수 없기 때문에 개체의 상태는 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82f4-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="a82f4-106">**오류 ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="a82f4-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a82f4-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a82f4-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="a82f4-108">참조 되는 멤버는 사용할 수 있는지 확인에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82f4-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="a82f4-109">와 함께 멤버를 명시적으로 한정 된 `Me` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a82f4-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82f4-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a82f4-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="a82f4-111">Dim 문</span><span class="sxs-lookup"><span data-stu-id="a82f4-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
