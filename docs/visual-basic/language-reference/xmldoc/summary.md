---
title: "&lt;요약&gt; (Visual Basic) | Microsoft 문서"
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
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
ms.openlocfilehash: 42321daf092c4b637d2f75fb7f6d7e95201791ba
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017

---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="c3e0b-102">&lt;요약&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3e0b-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="c3e0b-103">멤버의 요약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3e0b-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3e0b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3e0b-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c3e0b-106">개체의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3e0b-107">주의</span><span class="sxs-lookup"><span data-stu-id="c3e0b-107">Remarks</span></span>  
 <span data-ttu-id="c3e0b-108">사용 된 `<summary>` 형식 또는 형식 멤버를 설명 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="c3e0b-109">사용 하 여 [ \<설명 >](../../../visual-basic/language-reference/xmldoc/remarks.md) 유형 설명에 추가 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="c3e0b-110">에 대 한 텍스트는 `<summary>` 태그는 IntelliSense에는 형식에 대 한 정보의 유일 하는 소스 및 개체 브라우저에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="c3e0b-111">개체 브라우저에 대 한 정보를 참조 하십시오. [코드 구조 보기](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-111">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="c3e0b-112">사용 하 여 컴파일하면 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 문서 주석을 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3e0b-113">예제</span><span class="sxs-lookup"><span data-stu-id="c3e0b-113">Example</span></span>  
 <span data-ttu-id="c3e0b-114">사용 하 여이 예제는 `<summary>` 태그를 설명 하는 `ResetCounter` 메서드 및 `Counter` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e0b-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 <span data-ttu-id="c3e0b-115">[!code-vb[VbVbcnXmlDocComments #&1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c3e0b-115">[!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e0b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3e0b-116">See Also</span></span>  
 [<span data-ttu-id="c3e0b-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="c3e0b-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
