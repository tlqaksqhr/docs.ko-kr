---
title: '&lt;param&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c992c96303eb1441eaf667693b7aefb5361b196c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602923"
---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="0ee5f-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ee5f-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="0ee5f-103">매개 변수 이름 및 설명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ee5f-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ee5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ee5f-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0ee5f-106">메서드 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-106">The name of a method parameter.</span></span> <span data-ttu-id="0ee5f-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="0ee5f-108">매개 변수에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ee5f-109">설명</span><span class="sxs-lookup"><span data-stu-id="0ee5f-109">Remarks</span></span>  
 <span data-ttu-id="0ee5f-110">`<param>` 메서드에 대 한 매개 변수 중 하나를 설명 하기 위해 태그를 메서드 선언에 대 한 설명에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="0ee5f-111">에 대 한 텍스트는 `<param>` 태그는 다음 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="0ee5f-112">IntelliSense의 매개 변수 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="0ee5f-113">자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="0ee5f-114">개체 브라우저입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-114">Object Browser.</span></span> <span data-ttu-id="0ee5f-115">자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="0ee5f-116">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee5f-117">예제</span><span class="sxs-lookup"><span data-stu-id="0ee5f-117">Example</span></span>  
 <span data-ttu-id="0ee5f-118">사용 하 여이 예제는 `<param>` 태그를 설명 하는 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee5f-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0ee5f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ee5f-119">See Also</span></span>  
 [<span data-ttu-id="0ee5f-120">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="0ee5f-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
