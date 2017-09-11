---
title: "&lt;주의&gt; (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c1b2c48dc3247935f703ff4107f29829c494a305
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017

---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="e0be7-102">&lt;주의&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0be7-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="e0be7-103">멤버에 대 한 설명 부분을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0be7-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0be7-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0be7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0be7-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e0be7-106">멤버의 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0be7-107">주의</span><span class="sxs-lookup"><span data-stu-id="e0be7-107">Remarks</span></span>  
 <span data-ttu-id="e0be7-108">사용 된 `<remarks>` 으로 지정 된 정보를 보완 하는 형식에 대 한 정보를 추가 하는 태그 [ \<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="e0be7-109">이 정보는 개체 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="e0be7-110">개체 브라우저에 대 한 정보를 참조 하십시오. [코드 구조 보기](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-110">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="e0be7-111">사용 하 여 컴파일하면 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 문서 주석을 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0be7-112">예제</span><span class="sxs-lookup"><span data-stu-id="e0be7-112">Example</span></span>  
 <span data-ttu-id="e0be7-113">사용 하 여이 예제는 `<remarks>` 무엇 인지 설명 하는 태그는 `UpdateRecord` 메서드는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0be7-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 <span data-ttu-id="e0be7-114">[!code-vb[VbVbcnXmlDocComments #&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e0be7-114">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0be7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0be7-115">See Also</span></span>  
 [<span data-ttu-id="e0be7-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="e0be7-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
