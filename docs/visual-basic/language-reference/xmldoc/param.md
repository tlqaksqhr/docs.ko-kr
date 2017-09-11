---
title: "&lt;param&gt; (Visual Basic) | Microsoft 문서"
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
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
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
ms.openlocfilehash: ddf5baf83816d757edf67cdf1c66dc24e4313b83
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017

---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="83adb-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83adb-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="83adb-103">매개 변수 이름 및 설명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83adb-104">구문</span><span class="sxs-lookup"><span data-stu-id="83adb-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83adb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83adb-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="83adb-106">메서드 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-106">The name of a method parameter.</span></span> <span data-ttu-id="83adb-107">큰따옴표로 이름을 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="83adb-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="83adb-108">매개 변수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83adb-109">주의</span><span class="sxs-lookup"><span data-stu-id="83adb-109">Remarks</span></span>  
 <span data-ttu-id="83adb-110">`<param>` 태그를 메서드에 대 한 매개 변수 중 하나를 설명 하는 메서드 선언에 대 한 설명에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="83adb-111">에 대 한 텍스트는 `<param>` 태그는 다음 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="83adb-112">IntelliSense의 매개 변수 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="83adb-113">자세한 내용은 [IntelliSense 사용](https://docs.microsoft.com/visualstudio/ide/using-intellisense)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83adb-113">For more information, see [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="83adb-114">개체 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-114">Object Browser.</span></span> <span data-ttu-id="83adb-115">자세한 내용은 [코드 구조 보기](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83adb-115">For more information, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="83adb-116">사용 하 여 컴파일하면 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 문서 주석을 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83adb-117">예제</span><span class="sxs-lookup"><span data-stu-id="83adb-117">Example</span></span>  
 <span data-ttu-id="83adb-118">사용 하 여이 예제는 `<param>` 태그를 설명 하는 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="83adb-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 <span data-ttu-id="83adb-119">[!code-vb[VbVbcnXmlDocComments #&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="83adb-119">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83adb-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83adb-120">See Also</span></span>  
 [<span data-ttu-id="83adb-121">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="83adb-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
