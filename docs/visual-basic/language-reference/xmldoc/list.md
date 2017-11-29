---
title: "&lt;목록&gt; (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 34347df88f1bc3097db0020526ec99943c8f7bd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltlistgt-visual-basic"></a><span data-ttu-id="ab1fd-102">&lt;목록&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab1fd-102">&lt;list&gt; (Visual Basic)</span></span>
<span data-ttu-id="ab1fd-103">목록 또는 테이블을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab1fd-104">Syntax</span></span>  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab1fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab1fd-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="ab1fd-106">형식 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-106">The type of the list.</span></span> <span data-ttu-id="ab1fd-107">글머리 기호 목록, 번호 매기기 목록 또는 두 개의 열 테이블에 대 한 "table"에 대 한 "number"에 대 한 "bullet" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="ab1fd-108">경우에 사용 `type` "table"은</span><span class="sxs-lookup"><span data-stu-id="ab1fd-108">Only used when `type` is "table."</span></span> <span data-ttu-id="ab1fd-109">용어를 정의 하려면 설명 태그에 정의 된입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="ab1fd-110">때 `type` "bullet" 또는 "number" `description` 이 목록에 항목이 때 `type` "table"은 `description` 의 정의가 `term`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab1fd-111">설명</span><span class="sxs-lookup"><span data-stu-id="ab1fd-111">Remarks</span></span>  
 <span data-ttu-id="ab1fd-112">`<listheader>` 블록 목록 정의 또는 테이블의 머리글을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="ab1fd-113">테이블을 정의할 때만 제공 해야에 대 한 항목이 `term` 머리글에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="ab1fd-114">목록의 각 항목으로 지정 된 프로그램 `<item>` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="ab1fd-115">둘 다 지정 해야 정의 목록을 만들 때 `term` 및 `description`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="ab1fd-116">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록에 대 한 하기만 하면에 대 한 항목을 제공 하려면 `description`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="ab1fd-117">목록 또는 테이블 만큼 가질 수 `<item>` 필요에 따라 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="ab1fd-118">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab1fd-119">예제</span><span class="sxs-lookup"><span data-stu-id="ab1fd-119">Example</span></span>  
 <span data-ttu-id="ab1fd-120">사용 하 여이 예제는 `<list>` 글머리 기호 목록 주의 섹션에 정의 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fd-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ab1fd-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab1fd-121">See Also</span></span>  
 [<span data-ttu-id="ab1fd-122">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="ab1fd-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
