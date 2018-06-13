---
title: 기본 속성 &#39; &lt;propertyname1&gt; &#39; 기본 속성과 충돌 &#39; &lt;propertyname2&gt; &#39; 에 &#39; &lt;classname&gt; &#39;선언할 수 있으므로 &#39;그림자&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b305f7a59a9865ebeb6b6f53607757b719fb4d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586626"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="659ee-102">기본 속성 &#39; &lt;propertyname1&gt; &#39; 기본 속성과 충돌 &#39; &lt;propertyname2&gt; &#39; 에 &#39; &lt;classname&gt; &#39;선언할 수 있으므로 &#39;그림자&#39;</span><span class="sxs-lookup"><span data-stu-id="659ee-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="659ee-103">기본 클래스에 정의 된 속성과 동일한 이름을 가진 속성이 선언 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659ee-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="659ee-104">이 상황에서이 클래스에서 속성 기본 클래스 속성을 숨겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="659ee-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="659ee-105">이 메시지는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="659ee-105">This message is a warning.</span></span> <span data-ttu-id="659ee-106">기본적으로`Shadows` 로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="659ee-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="659ee-107">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="659ee-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="659ee-108">**오류 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="659ee-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="659ee-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="659ee-109">To correct this error</span></span>  
  
-   <span data-ttu-id="659ee-110">추가 `Shadows` 속성의 이름에서 선언 되 키워드를 선언 또는 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="659ee-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659ee-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="659ee-111">See Also</span></span>  
 [<span data-ttu-id="659ee-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="659ee-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="659ee-113">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="659ee-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
