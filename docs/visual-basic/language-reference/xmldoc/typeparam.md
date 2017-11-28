---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b654fe6fc93642693730256b523fee999aa55937
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="2aecd-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aecd-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="2aecd-103">형식 매개 변수 이름 및 설명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aecd-104">구문</span><span class="sxs-lookup"><span data-stu-id="2aecd-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2aecd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2aecd-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2aecd-106">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-106">The name of the type parameter.</span></span> <span data-ttu-id="2aecd-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2aecd-108">형식 매개 변수 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2aecd-109">설명</span><span class="sxs-lookup"><span data-stu-id="2aecd-109">Remarks</span></span>  
 <span data-ttu-id="2aecd-110">사용 하 여는 `<typeparam>` 태그에는 제네릭 형식 또는 제네릭 멤버 선언에서 형식 매개 변수 중 하나를 설명에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="2aecd-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aecd-112">예제</span><span class="sxs-lookup"><span data-stu-id="2aecd-112">Example</span></span>  
 <span data-ttu-id="2aecd-113">사용 하 여이 예제는 `<typeparam>` 태그를 설명 하는 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2aecd-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2aecd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2aecd-114">See Also</span></span>  
 [<span data-ttu-id="2aecd-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="2aecd-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
