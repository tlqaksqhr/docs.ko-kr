---
title: '&lt;paramref&gt;(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 0b0d49b90e097e23d3878281f9accda14b057720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325135"
---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="15c39-102">&lt;paramref&gt;(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="15c39-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="15c39-103">구문</span><span class="sxs-lookup"><span data-stu-id="15c39-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15c39-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15c39-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="15c39-105">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="15c39-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="15c39-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="15c39-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15c39-107">설명</span><span class="sxs-lookup"><span data-stu-id="15c39-107">Remarks</span></span>  
 <span data-ttu-id="15c39-108">\<paramref> 태그를 사용하면 \<summary>, \<remarks> 블록 등의 코드 주석에 포함된 단어가 매개 변수를 참조함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c39-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="15c39-109">XML 파일을 처리하여 굵게, 기울임꼴 글꼴 등의 고유한 방식으로 이 단어에 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c39-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="15c39-110">[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="15c39-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15c39-111">예</span><span class="sxs-lookup"><span data-stu-id="15c39-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="15c39-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15c39-112">See Also</span></span>  
 [<span data-ttu-id="15c39-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="15c39-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="15c39-114">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="15c39-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
