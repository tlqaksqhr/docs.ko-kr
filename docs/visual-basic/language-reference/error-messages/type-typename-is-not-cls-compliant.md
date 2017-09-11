---
title: "형식 &lt;typename&gt; CLS 규격이 아닌 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
dev_langs:
- VB
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
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
ms.openlocfilehash: a8d65568e862c941d5b927582833dff803219bf9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="967fb-102">형식 &lt;typename&gt; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="967fb-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="967fb-103">변수, 속성 또는 함수 반환 CLS 호환 되지 않는 데이터 형식으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="967fb-104">와 호환 되도록 응용 프로그램은 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS ()를 CLS 규격 형식에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-104">For an application to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="967fb-105">다음 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-105">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="967fb-106">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="967fb-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="967fb-107">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="967fb-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="967fb-108">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="967fb-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="967fb-109">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="967fb-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="967fb-110">**오류 ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="967fb-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="967fb-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="967fb-111">To correct this error</span></span>  
  
-   <span data-ttu-id="967fb-112">응용 프로그램 CLS 규격 이어야 하는 경우 가장 가까운 CLS 규격 형식으로이 요소의 데이터 형식을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="967fb-113">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="967fb-114">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="967fb-115">응용 프로그램에서는 CLS 규격 필요가 없는 경우 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="967fb-116">그러나 비 호환성 인식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="967fb-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967fb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="967fb-117">See Also</span></span>  
 [<span data-ttu-id="967fb-118">\<통해 PAVE > CLS 규격 코드 작성</span><span class="sxs-lookup"><span data-stu-id="967fb-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
