---
title: '&lt;paramref&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 763e311dfb46ceeed358c3b3bebd6212d3e2489c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598664"
---
# <a name="ltparamrefgt-visual-basic"></a><span data-ttu-id="ab8de-102">&lt;paramref&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab8de-102">&lt;paramref&gt; (Visual Basic)</span></span>
<span data-ttu-id="ab8de-103">단어를 매개 변수로 서식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab8de-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab8de-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab8de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab8de-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ab8de-106">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="ab8de-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab8de-108">설명</span><span class="sxs-lookup"><span data-stu-id="ab8de-108">Remarks</span></span>  
 <span data-ttu-id="ab8de-109">`<paramref>` 태그는 단어는 매개 변수를 표시 하는 방식이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="ab8de-110">다른 방식으로이 매개 변수 형식을 지정 하려면 XML 파일을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="ab8de-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab8de-112">예제</span><span class="sxs-lookup"><span data-stu-id="ab8de-112">Example</span></span>  
 <span data-ttu-id="ab8de-113">사용 하 여이 예제는 `<paramref>` 참조 하는 태그는 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab8de-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ab8de-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab8de-114">See Also</span></span>  
 [<span data-ttu-id="ab8de-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="ab8de-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
