---
title: "&lt;param&gt;(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
dev_langs:
- CSharp
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1076405d60c85540eeaeba39821bd20bc628030d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="c79a5-102">&lt;param&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c79a5-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c79a5-103">구문</span><span class="sxs-lookup"><span data-stu-id="c79a5-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c79a5-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c79a5-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c79a5-105">메서드 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-105">The name of a method parameter.</span></span> <span data-ttu-id="c79a5-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c79a5-107">매개 변수에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c79a5-108">설명</span><span class="sxs-lookup"><span data-stu-id="c79a5-108">Remarks</span></span>  
 <span data-ttu-id="c79a5-109">\<param> 태그는 메서드의 매개 변수 중 하나를 설명하기 위해 메서드 선언에 대한 주석에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="c79a5-110">여러 매개 변수를 문서화하려면 여러 개의 \<param> 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="c79a5-111">\<param> 태그에 대한 텍스트는 IntelliSense, 개체 브라우저 및 코드 주석 웹 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="c79a5-112">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c79a5-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c79a5-113">예제</span><span class="sxs-lookup"><span data-stu-id="c79a5-113">Example</span></span>  
 <span data-ttu-id="c79a5-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c79a5-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79a5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c79a5-115">See Also</span></span>  
 <span data-ttu-id="c79a5-116">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c79a5-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c79a5-117">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="c79a5-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

