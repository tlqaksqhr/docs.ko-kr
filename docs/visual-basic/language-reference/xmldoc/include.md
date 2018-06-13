---
title: '&lt;포함&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 65bc0439696612cd8331a9c0718efcfee83af574
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602738"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="a76c4-102">&lt;포함&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a76c4-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="a76c4-103">형식 및 소스 코드에서 멤버를 설명 하는 다른 파일을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a76c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="a76c4-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a76c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a76c4-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="a76c4-106">필수.</span><span class="sxs-lookup"><span data-stu-id="a76c4-106">Required.</span></span> <span data-ttu-id="a76c4-107">설명서를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="a76c4-108">경로를 사용하여 파일 이름을 정규화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="a76c4-109">묶습니다 `filename` 큰따옴표에서 ("").</span><span class="sxs-lookup"><span data-stu-id="a76c4-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="a76c4-110">필수.</span><span class="sxs-lookup"><span data-stu-id="a76c4-110">Required.</span></span> <span data-ttu-id="a76c4-111">`filename`의 태그 경로로, `name` 태그에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="a76c4-112">경로를 큰따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="a76c4-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="a76c4-113">필수.</span><span class="sxs-lookup"><span data-stu-id="a76c4-113">Required.</span></span> <span data-ttu-id="a76c4-114">주석 앞에 태그에 이름 지정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="a76c4-115">`Name` 갖습니다는 `id`합니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="a76c4-116">필수.</span><span class="sxs-lookup"><span data-stu-id="a76c4-116">Required.</span></span> <span data-ttu-id="a76c4-117">주석 앞에 오는 태그의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="a76c4-118">ID를 작은따옴표로 묶습니다 (' ').</span><span class="sxs-lookup"><span data-stu-id="a76c4-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a76c4-119">설명</span><span class="sxs-lookup"><span data-stu-id="a76c4-119">Remarks</span></span>  
 <span data-ttu-id="a76c4-120">사용 하 여는 `<include>` 태그의 형식을 설명 하는 다른 파일의 주석에 소스 코드에서 멤버를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="a76c4-121">소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="a76c4-122">`<include>` 태그의 W3C XML 경로 언어 (XPath) Version 1.0 권장 사항에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="a76c4-123">사용자 지정 하는 방법에 대 한 자세한 내용은 프로그램 `<include>` 사용에서 제공 됩니다. http://www.w3.org/TR/xpath합니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a76c4-124">예제</span><span class="sxs-lookup"><span data-stu-id="a76c4-124">Example</span></span>  
 <span data-ttu-id="a76c4-125">사용 하 여이 예제는 `<include>` 멤버 문서 주석을 라는 파일에서 가져올 태그 `commentFile.xml`합니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="a76c4-126">형식은 `commentFile.xml` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a76c4-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a76c4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a76c4-127">See Also</span></span>  
 [<span data-ttu-id="a76c4-128">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="a76c4-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
