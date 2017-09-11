---
title: "&quot;&lt;interfacename&gt;.&lt; membername&gt;&quot;가 이미 구현 된 기본 클래스에서 &quot;&lt;baseclassname&gt;&quot;. 재구현 &lt;형식&gt; 가정 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
dev_langs:
- VB
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d792485f13e2b675858d82aa7219670a17fd974e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="5f984-103">'&lt;interfacename&gt;.&lt; membername&gt;'가 이미 구현 된 기본 클래스에서 '&lt;baseclassname&gt;'.</span><span class="sxs-lookup"><span data-stu-id="5f984-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="5f984-104">재구현 &lt;형식&gt; 가정</span><span class="sxs-lookup"><span data-stu-id="5f984-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="5f984-105">속성, 프로시저 또는 파생된 클래스에서 이벤트를 사용 하는 `Implements` 절을 기본 클래스에서 이미 구현 된 인터페이스 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="5f984-106">파생 클래스는 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="5f984-107">이는 기본 클래스 구현 재정의와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="5f984-108">자세한 내용은 참조 [구현](../../../visual-basic/language-reference/statements/implements-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="5f984-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-109">By default, this message is a warning.</span></span> <span data-ttu-id="5f984-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f984-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5f984-111">**오류 ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="5f984-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f984-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5f984-112">To correct this error</span></span>  
  
-   <span data-ttu-id="5f984-113">인터페이스 멤버를 다시 구현하려는 경우 어떤 조치도 취할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="5f984-114">파생된 클래스에서 코드를 사용 하지 않으면 재구현된 멤버에 액세스는 `MyBase` 키워드를 기본 클래스 구현에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="5f984-115">인터페이스 멤버를 다시 구현하지 않으려는 경우 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5f984-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f984-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f984-116">See Also</span></span>  
 [<span data-ttu-id="5f984-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f984-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
