---
title: '&#39;&lt;membername&gt; &#39; 형식을 노출할 수 없습니다 &#39; &lt;typename&gt; &#39; 통해 프로젝트 외부 &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 36add48ebee2d1804921eeeec0b59cdd4cbafecc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588095"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="c076c-102">&#39;&lt;membername&gt; &#39; 형식을 노출할 수 없습니다 &#39; &lt;typename&gt; &#39; 통해 프로젝트 외부 &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="c076c-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="c076c-103">해당 컨테이너 외부 노출 되는 변수, 프로시저, 매개 변수 또는 함수 반환 하지만 컨테이너 외부 노출 되어서는 안 되는 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c076c-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="c076c-104">다음 기본 코드에서는이 오류를 생성 하는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c076c-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="c076c-105">선언 된 형식을 `Protected`, `Friend`, `Protected Friend`, 또는 `Private` 해당 선언 컨텍스트 외부 액세스가 제한 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c076c-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="c076c-106">사용 하 여 데이터와 덜 제한적인된 액세스로 변수 형식을 맞지 않게이 목적입니다.</span><span class="sxs-lookup"><span data-stu-id="c076c-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="c076c-107">앞의 기본 코드에서 `exposedVar` 은 `Public` 노출 합니다 `privateClass` 에 액세스할 수 없는 코드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c076c-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="c076c-108">**오류 ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="c076c-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c076c-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c076c-109">To correct this error</span></span>  
  
-   <span data-ttu-id="c076c-110">해당 데이터 형식의 액세스 수준으로 제한적 이어야 반환 되는 변수, 프로시저, 매개 변수 또는 함수 형식의 액세스 수준을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c076c-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c076c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c076c-111">See Also</span></span>  
 [<span data-ttu-id="c076c-112">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="c076c-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
