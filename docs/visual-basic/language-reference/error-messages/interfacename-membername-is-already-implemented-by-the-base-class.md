---
title: '&#39;&lt;interfacename&gt;.&lt; membername&gt; &#39; 기본 클래스에 의해 이미 구현 &#39; &lt;baseclassname&gt;&#39;합니다. 다시 구현 &lt;형식&gt; 가정'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588972"
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="33867-103">&#39;&lt;interfacename&gt;.&lt; membername&gt; &#39; 기본 클래스에 의해 이미 구현 &#39; &lt;baseclassname&gt;&#39;합니다.</span><span class="sxs-lookup"><span data-stu-id="33867-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="33867-104">다시 구현 &lt;형식&gt; 가정</span><span class="sxs-lookup"><span data-stu-id="33867-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="33867-105">속성, 프로시저 또는 파생된 클래스에서 이벤트를 사용 하는 `Implements` 절을 이미 기본 클래스에서 구현 된 인터페이스 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33867-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="33867-106">파생 클래스는 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33867-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="33867-107">이는 기본 클래스 구현 재정의와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="33867-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="33867-108">자세한 내용은 참조 [구현](../../../visual-basic/language-reference/statements/implements-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33867-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="33867-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="33867-109">By default, this message is a warning.</span></span> <span data-ttu-id="33867-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33867-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="33867-111">**오류 ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="33867-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33867-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="33867-112">To correct this error</span></span>  
  
-   <span data-ttu-id="33867-113">인터페이스 멤버를 다시 구현하려는 경우 어떤 조치도 취할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33867-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="33867-114">사용 하지 않는 경우 파생된 클래스의 코드가 다시 구현 된 멤버에 액세스는 `MyBase` 키워드를 기본 클래스 구현에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="33867-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="33867-115">인터페이스 멤버를 다시 구현하지 않으려는 경우 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="33867-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33867-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33867-116">See Also</span></span>  
 [<span data-ttu-id="33867-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="33867-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
