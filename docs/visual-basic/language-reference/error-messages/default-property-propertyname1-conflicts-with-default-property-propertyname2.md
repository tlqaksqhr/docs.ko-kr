---
title: "기본 속성 &quot;&lt;propertyname1&gt;&quot;기본 속성을 사용 하 여 충돌&quot;&lt;propertyname2&gt;&quot;에서&quot;&lt;classname&gt;&quot; &quot;Shadows&quot; 선언할 수 있으므로 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
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
ms.openlocfilehash: 6eac9e0fdc468e27afac82a8a7c9b2251a8f7317
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="45489-102">기본 속성 '&lt;propertyname1&gt;'기본 속성을 사용 하 여 충돌'&lt;propertyname2&gt;'에서'&lt;classname&gt;' 'Shadows' 선언할 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="45489-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="45489-103">기본 클래스에 정의 된 속성과 동일한 이름을 가진 속성이 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45489-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="45489-104">이 상황에서이 클래스의 속성이 기본 클래스 속성을 숨겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45489-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="45489-105">이 메시지는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="45489-105">This message is a warning.</span></span> <span data-ttu-id="45489-106">`Shadows`기본적으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45489-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="45489-107">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="45489-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="45489-108">**오류 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="45489-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45489-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="45489-109">To correct this error</span></span>  
  
-   <span data-ttu-id="45489-110">추가 `Shadows` 속성의 이름에서 선언 되 키워드를 선언 하거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="45489-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45489-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45489-111">See Also</span></span>  
 <span data-ttu-id="45489-112">[그림자](../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="45489-112">[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="45489-113"> [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span><span class="sxs-lookup"><span data-stu-id="45489-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span></span>
