---
title: "값 형식 &#39; type1 &#39; 변환할 수 없습니다 &#39; 유형 2 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords: BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="a8f71-102">값 형식 &#39; type1 &#39; 변환할 수 없습니다 &#39; 유형 2 &#39;</span><span class="sxs-lookup"><span data-stu-id="a8f71-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="a8f71-103">'Type1' 형식의 값을 'type2'로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f71-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="a8f71-104">'Value' 속성을 사용 하 여 첫 번째 요소의 문자열 값을 가져올 '\<parentElement >'입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f71-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="a8f71-105">XML 리터럴을 특정 형식으로 암시적으로 캐스팅하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f71-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="a8f71-106">XML 리터럴은 지정된 형식으로 암시적으로 캐스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f71-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="a8f71-107">**오류 ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="a8f71-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8f71-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a8f71-108">To correct this error</span></span>  
  
-   <span data-ttu-id="a8f71-109">XML 리터럴의 `Value` 속성을 사용하여 해당 값을 `String`으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f71-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="a8f71-110">`CType` 함수, 다른 형식 변환 함수 또는 <xref:System.Convert> 클래스를 사용하여 지정된 형식으로 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f71-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f71-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8f71-111">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="a8f71-112">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a8f71-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a8f71-113">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="a8f71-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="a8f71-114">XML</span><span class="sxs-lookup"><span data-stu-id="a8f71-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
