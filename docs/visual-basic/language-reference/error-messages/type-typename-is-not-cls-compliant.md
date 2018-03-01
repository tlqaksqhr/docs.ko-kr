---
title: "형식 &lt;typename&gt; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36a49ccf7d2185c26ef8d23eebea216cc193d951
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="78127-102">형식 &lt;typename&gt; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="78127-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="78127-103">변수, 속성 또는 함수 반환는 CLS 호환 되지 않는 데이터 형식으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78127-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="78127-104">과 호환 되도록 응용 프로그램에 대 한는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS) CLS 규격 형식만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78127-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="78127-105">다음 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="78127-105">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="78127-106">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="78127-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="78127-107">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="78127-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="78127-108">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="78127-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="78127-109">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="78127-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="78127-110">**오류 ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="78127-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="78127-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="78127-111">To correct this error</span></span>  
  
-   <span data-ttu-id="78127-112">응용 프로그램을 CLS 규격을 준수 해야 하는 경우 가장 가까운 CLS 규격 형식이 요소의 데이터 형식을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="78127-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="78127-113">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78127-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="78127-114">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78127-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="78127-115">응용 프로그램에 CLS 규격이 될 필요가 없는 경우 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78127-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="78127-116">그러나 해당 규칙 위반 인식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78127-116">You should be aware of its noncompliance, however.</span></span>