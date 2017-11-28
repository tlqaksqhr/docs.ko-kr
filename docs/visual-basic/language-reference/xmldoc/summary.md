---
title: "&lt;요약&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2a3008d1393c44aa0ec2398a2bd6afa079013e7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="82e28-102">&lt;요약&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82e28-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="82e28-103">멤버의 요약 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e28-104">구문</span><span class="sxs-lookup"><span data-stu-id="82e28-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82e28-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82e28-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="82e28-106">개체에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82e28-107">설명</span><span class="sxs-lookup"><span data-stu-id="82e28-107">Remarks</span></span>  
 <span data-ttu-id="82e28-108">사용 된 `<summary>` 형식 또는 형식 멤버를 설명 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="82e28-109">[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="82e28-110">에 대 한 텍스트는 `<summary>` 태그가 유일한 소스 intellisense에서 유형에 대 한 정보는이 고 개체 브라우저에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="82e28-111">개체 브라우저에 대 한 정보를 참조 하십시오. [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)합니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="82e28-112">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82e28-113">예제</span><span class="sxs-lookup"><span data-stu-id="82e28-113">Example</span></span>  
 <span data-ttu-id="82e28-114">사용 하 여이 예제는 `<summary>` 태그를 설명 하는 `ResetCounter` 메서드 및 `Counter` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="82e28-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="82e28-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82e28-115">See Also</span></span>  
 [<span data-ttu-id="82e28-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="82e28-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
