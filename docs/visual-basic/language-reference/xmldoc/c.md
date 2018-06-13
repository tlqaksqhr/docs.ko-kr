---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 556c00fa761a1bce5e922a304706c78893550901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599608"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="18746-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18746-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="18746-103">설명 텍스트는 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18746-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18746-104">구문</span><span class="sxs-lookup"><span data-stu-id="18746-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18746-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18746-105">Parameters</span></span>  
  
|<span data-ttu-id="18746-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18746-106">Parameter</span></span>|<span data-ttu-id="18746-107">설명</span><span class="sxs-lookup"><span data-stu-id="18746-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="18746-108">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="18746-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18746-109">설명</span><span class="sxs-lookup"><span data-stu-id="18746-109">Remarks</span></span>  
 <span data-ttu-id="18746-110">`<c>` 태그 사용 방법을 나타내는 설명에 대 한 텍스트 코드로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18746-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="18746-111">여러 줄을 코드로 지정하려면 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18746-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="18746-112">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="18746-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18746-113">예제</span><span class="sxs-lookup"><span data-stu-id="18746-113">Example</span></span>  
 <span data-ttu-id="18746-114">사용 하 여이 예제는 `<c>` 임을 나타내는 요약 섹션에는 태그 `Counter` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18746-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="18746-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18746-115">See Also</span></span>  
 [<span data-ttu-id="18746-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="18746-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
