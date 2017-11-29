---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e57cae8fd4b93fee59992d717135ad7d3d78be5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="af056-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af056-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="af056-103">설명 텍스트는 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af056-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af056-104">구문</span><span class="sxs-lookup"><span data-stu-id="af056-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af056-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af056-105">Parameters</span></span>  
  
|<span data-ttu-id="af056-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af056-106">Parameter</span></span>|<span data-ttu-id="af056-107">설명</span><span class="sxs-lookup"><span data-stu-id="af056-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="af056-108">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="af056-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af056-109">설명</span><span class="sxs-lookup"><span data-stu-id="af056-109">Remarks</span></span>  
 <span data-ttu-id="af056-110">`<c>` 태그 사용 방법을 나타내는 설명에 대 한 텍스트 코드로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af056-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="af056-111">여러 줄을 코드로 지정하려면 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af056-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="af056-112">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="af056-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af056-113">예제</span><span class="sxs-lookup"><span data-stu-id="af056-113">Example</span></span>  
 <span data-ttu-id="af056-114">사용 하 여이 예제는 `<c>` 임을 나타내는 요약 섹션에는 태그 `Counter` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="af056-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="af056-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af056-115">See Also</span></span>  
 [<span data-ttu-id="af056-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="af056-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
