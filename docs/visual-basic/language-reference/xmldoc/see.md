---
title: '&lt;참조&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e790f8abd216e198ff5077beab6f857e39981d2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602082"
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="8b778-102">&lt;참조&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b778-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="8b778-103">다른 멤버에 대 한 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b778-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b778-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b778-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b778-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="8b778-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="8b778-107">지정 된 코드 요소가 있고 전달 컴파일러 확인 `member` 출력 XML에에서 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="8b778-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b778-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b778-109">Remarks</span></span>  
 <span data-ttu-id="8b778-110">사용 하 여는 `<see>` 태그를 텍스트 내부에서 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="8b778-111">사용 하 여 [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) "참조 항목" 섹션에 나타낼 수 있는 텍스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="8b778-112">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8b778-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b778-113">예제</span><span class="sxs-lookup"><span data-stu-id="8b778-113">Example</span></span>  
 <span data-ttu-id="8b778-114">사용 하 여이 예제는 `<see>` 에 태그는 `UpdateRecord` 설명 부분을 참조 하는 `DoesRecordExist` 메서드.</span><span class="sxs-lookup"><span data-stu-id="8b778-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8b778-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b778-115">See Also</span></span>  
 [<span data-ttu-id="8b778-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="8b778-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
