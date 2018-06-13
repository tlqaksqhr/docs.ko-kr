---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 76e0e8d4757f29bb5df82ea1482beff3dd43c0e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598016"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="f0678-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0678-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="f0678-103">형식 매개 변수 이름 및 설명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0678-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0678-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0678-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0678-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f0678-106">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-106">The name of the type parameter.</span></span> <span data-ttu-id="f0678-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f0678-108">형식 매개 변수 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0678-109">설명</span><span class="sxs-lookup"><span data-stu-id="f0678-109">Remarks</span></span>  
 <span data-ttu-id="f0678-110">사용 하 여는 `<typeparam>` 태그에는 제네릭 형식 또는 제네릭 멤버 선언에서 형식 매개 변수 중 하나를 설명에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="f0678-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0678-112">예제</span><span class="sxs-lookup"><span data-stu-id="f0678-112">Example</span></span>  
 <span data-ttu-id="f0678-113">사용 하 여이 예제는 `<typeparam>` 태그를 설명 하는 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f0678-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f0678-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0678-114">See Also</span></span>  
 [<span data-ttu-id="f0678-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="f0678-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
