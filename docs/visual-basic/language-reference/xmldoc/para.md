---
title: '&lt;p a r a&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: cb80f4b39bee128790b311732adf1202dbbc6993
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601727"
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="04136-102">&lt;p a r a&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04136-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="04136-103">콘텐츠를 단락으로 포맷 되어 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04136-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04136-104">구문</span><span class="sxs-lookup"><span data-stu-id="04136-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04136-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04136-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="04136-106">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="04136-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04136-107">설명</span><span class="sxs-lookup"><span data-stu-id="04136-107">Remarks</span></span>  
 <span data-ttu-id="04136-108">`<para>` 태그와 같은 태그 내에서 사용할는 [ \<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<설명 >](../../../visual-basic/language-reference/xmldoc/remarks.md), 또는 [ \<반환 >](../../../visual-basic/language-reference/xmldoc/returns.md), 텍스트에 구조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04136-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="04136-109">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="04136-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04136-110">예제</span><span class="sxs-lookup"><span data-stu-id="04136-110">Example</span></span>  
 <span data-ttu-id="04136-111">사용 하 여이 예제는 `<para>` 태그에 대 한 설명 부분을 분할 하는 `UpdateRecord` 두 단락으로 메서드.</span><span class="sxs-lookup"><span data-stu-id="04136-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04136-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04136-112">See Also</span></span>  
 [<span data-ttu-id="04136-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="04136-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
